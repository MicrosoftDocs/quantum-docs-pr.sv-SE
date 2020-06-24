---
title: Läsa in ett hamiltonskt värde från en fil
description: Lär dig hur du automatiskt genererar en stor Hamiltonian med Broombridge-schemat.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275246"
---
# <a name="loading-a-hamiltonian-from-file"></a>Läsa in ett hamiltonskt värde från en fil
Tidigare konstruerade vi Hamiltonians genom att lägga till enskilda villkor till den. Även om det här är bra för små exempel kräver Quantum kemi i skala Hamiltonians med miljon tals eller miljarder villkor. Sådana Hamiltonians, som genereras av kemi-paket som NWChem, är för stora för att kunna importeras manuellt. I det här exemplet illustrerar vi hur en `FermionHamiltonian` instans kan genereras automatiskt från en molekyl som representeras av [Broombridge-schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). En kan till exempel granska det tillhandahållna `LithiumHydrideGUI` exemplet eller `RunSimulation` exemplet. Begränsad support är också tillgängligt för import från formatet som används av [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Låt oss titta på exemplet på en kväve molekyl, som finns i `IntegralData/YAML` mappen i exempel databasen. Metoden för att läsa in `Broombridge` schemat är enkel.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Broombridge-schemat innehåller också förslag på det inledande tillstånd som ska förberedas. Etiketterna, t. ex. `"|G⟩"` eller `"|E1⟩"` , för dessa tillstånd kan ses genom att du inspekterar filen. För att förbereda de här inledande tillstånden kommer den `qSharpData` förbrukade delen av Q # Quantum-algoritmerna att få liknande [föregående avsnitt](xref:microsoft.quantum.chemistry.examples.energyestimate), men med ytterligare en parameter som väljer det ursprungliga tillståndet. Till exempel,
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Alla stegen ovan kan förkortas med hjälp av de praktiska metoder som följer.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

Vi kan också läsa in en Hamiltonian från LIQUi |> format med hjälp av en liknande syntax. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Genom att följa den här processen från en instans av Broombridge eller något mellanliggande steg, kan Quantum-algoritmer som uppskattning av Quantum-fasen köras på det angivna elektroniska struktur problemet.
