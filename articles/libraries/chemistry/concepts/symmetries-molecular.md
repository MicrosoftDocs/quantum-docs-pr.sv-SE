---
title: Symmetries av molekyl integraler | Microsoft Docs
description: Symmetries av koncept dokument för molekyl integraler
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442388"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries av molekyl integraler

Den inneboende symmetrin för Coulomb-Hamiltonian, som är den Hamiltonian som anges i [Quantum-modeller för elektroniska system](xref:microsoft.quantum.chemistry.concepts.quantummodels), som beskriver electrons interagerar elektriskt med varandra och med kärnor, leder till ett antal symmetries som kan utnyttjas för att komprimera villkoren i Hamiltonian.
I allmänhet om inga ytterligare antaganden görs om bas funktionerna $ \psi_j $ har vi bara den \begin{Equation} H_ {PQRS} = H_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation} som kan visas direkt från integralerna i [Quantum modeller för Elektroniska system](xref:microsoft.quantum.chemistry.concepts.quantummodels) som antecknar att deras värden är identiska om $p, q $ och $r, s $, är utbytbara från anti-Arbetssläckning.

Om vi antar att rotations avtrycken är Real värde (som de är för Gaussisk orbital Bases) har vi ytterligare \begin{Equation} H_ {PQRS} = H_ {qpsr} = H_ {srqp} = H_ {rspq} = H_ {rqps} = H_ {psrq} = H_ {SPQR} = H_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{ ekvation} vissa antaganden är undantagna, vi kan använda ovanstående symmetries för att minska de data som behövs för att lagra mat ris elementen i Hamiltonian med en faktor på $8 $; även om du gör det blir det något mer utmanande att importera data på ett konsekvent sätt.
Lyckligt vis har Hamiltonian Simulator-biblioteket Under rutiner som kan användas för att importera integral-filer från antingen [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) eller direkt från [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

Molekyl orbital integraler (d.v.s. $h\_{PQ} $ och $h\_{PQRS} $ villkor) som representeras med `OrbitalIntegral` typ, som innehåller ett antal användbara funktioner för att uttrycka denna symmetri.
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

Förutom att räkna upp alla orbital integraler som är numeriskt identiska, kan en lista över alla orbital-index som finns i Hamiltonian som representeras av en `OrbitalIntegral` genereras på följande sätt.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Konstruera Fermionic-Hamiltonians från molekyl integraler

I stället för att skapa en Fermionic-Hamiltonian genom att lägga till `FermionTerm`s, kan alla villkor som motsvarar varje orbital-integral läggas till automatiskt.
Följande kod räknar till exempel automatiskt över alla permutationer symmetries och beställer villkoren i kanonisk ordning: 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```