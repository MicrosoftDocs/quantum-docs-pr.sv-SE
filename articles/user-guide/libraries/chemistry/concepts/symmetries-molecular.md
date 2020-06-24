---
title: Symmetries av molekyl integraler
description: 'Lär dig mer om att använda Q # OrbitalIntegral-typen för att räkna upp molekyl symmetries.'
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275249"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="2ffac-103">Symmetries av molekyl integraler</span><span class="sxs-lookup"><span data-stu-id="2ffac-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="2ffac-104">Den ensymmetrien av Coulomb-Hamiltonian, som är den Hamiltonian som anges i [Quantum-modeller för elektroniska system](xref:microsoft.quantum.chemistry.concepts.quantummodels), som beskriver electrons interagerar med varandra och med kärnor, leder till ett antal symmetries som kan utnyttjas för att komprimera villkoren i Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2ffac-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="2ffac-105">I allmänhet om inga ytterligare antaganden görs om bas funktionerna $ \ psi_j $, har vi bara det \begin{Equation} h_ {PQRS} = h_ {qpsr}. \tag{★} \label{EQ: hpqrs} \end{Equation} som kan ses direkt från integralerna i [Quantum-modeller för elektroniska system](xref:microsoft.quantum.chemistry.concepts.quantummodels) när de antecknar att deras värden är identiska om $p, q $ och $r, s $ är utbytbara mot arbets tiden.</span><span class="sxs-lookup"><span data-stu-id="2ffac-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="2ffac-106">Om vi antar att rotations avtrycken är Real värde (som de är för Gaussisk orbital Bases) har vi ytterligare \begin{Equation} h_ {PQRS} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation} har gett oss sådana antaganden. vi kan använda ovanstående symmetries för att minska de data som behövs för att lagra mat ris elementen i Hamiltonian med en faktor på $8 $; även om du gör det blir det något mer utmanande att importera data på ett konsekvent sätt.</span><span class="sxs-lookup"><span data-stu-id="2ffac-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="2ffac-107">Lyckligt vis har Hamiltonian Simulator-biblioteket Under rutiner som kan användas för att importera integral-filer från antingen [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) eller direkt från [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="2ffac-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="2ffac-108">Molekyl orbital integraler (d.v.s. $h \_ {PQ} $ och $h \_ {PQRS} $ villkor) som representeras av `OrbitalIntegral` typen, vilket ger ett antal användbara funktioner för att uttrycka denna symmetri.</span><span class="sxs-lookup"><span data-stu-id="2ffac-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
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

<span data-ttu-id="2ffac-109">Förutom att räkna upp alla orbital integraler som är numeriskt identiska, kan en lista över alla orbital-index som finns i Hamiltonian som representeras av a `OrbitalIntegral` genereras på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="2ffac-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="2ffac-110">Konstruera Fermionic-Hamiltonians från molekyl integraler</span><span class="sxs-lookup"><span data-stu-id="2ffac-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="2ffac-111">I stället för att skapa en Fermionic-Hamiltonian genom att lägga till en `FermionTerm` , kan alla villkor som motsvarar varje orbital-integral läggas till automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2ffac-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="2ffac-112">Följande kod räknar till exempel automatiskt över alla permutationer symmetries och beställer villkoren i kanonisk ordning:</span><span class="sxs-lookup"><span data-stu-id="2ffac-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
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
