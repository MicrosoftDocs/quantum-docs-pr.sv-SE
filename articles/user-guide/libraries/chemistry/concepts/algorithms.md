---
title: Simulera Hamiltonian Dynamics
description: Lär dig hur du använder Trotter-Suzuki formler och qubitization för att arbeta med Hamiltonian-simuleringar.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: eeaa13b99ab07ce22f8a3306a756bf7ac7cde65b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857597"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulera Hamiltonian Dynamics

När Hamiltonian har utsetts som en summa av element operatörer kan Dynamics kompileras till grundläggande grind åtgärder med hjälp av en värd med välkända tekniker.
Det finns tre effektiva metoder som är Trotter – Suzuki formler, linjära kombinationer av unitaries och qubitization.
Vi förklarar dessa tre metoder och ger konkreta Q# exempel på hur du implementerar dessa metoder med Hamiltonian Simulator Library.


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki formler
Idén bakom Trotter – Suzuki formler är enkla: uttrycka Hamiltonian som en summa av enkel för att simulera Hamiltonians och sedan uppskatta den totala utvecklingen som en följd av dessa enklare utvecklingar.
I synnerhet ska $H = \ sum_ {j = 1} ^ m H_j $ vara Hamiltonian.
Sedan $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, vilket innebär att om $t \ll $1, blir felet i den här uppskattningen försumbar.
Observera att om $e ^ {-i H t} $ var en vanlig exponent, skulle felet i den här uppskattningen inte vara $O (m ^ 2 t ^ 2) $: det skulle vara noll.
Det här felet beror på att $e ^ {-iHt} $ är en operator exponentiell och därför att det uppstår ett fel när du använder den här formeln på grund av att $H _j $-villkoren inte går ut (*d.v.s.*$H _J H_k \ne H_k $ i allmänhet).

Om $t $ är stor kan Trotter – Suzuki-formler fortfarande användas för att simulera Dynamicset korrekt genom att dela upp det i en sekvens med korta tids steg.
Låt $r $ vara det antal steg som har vidtagits under tids utvecklingen, så varje gång steg körs för tid $t/r $. Sedan har vi den $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ höger) ^ r + O (m ^ 2 t ^ 2/r). $ $ som innebär att om $r $ skalas som $m ^ 2 t ^ 2/\ Epsilon $ kan felet göras högst $ \epsilon $ för alla $ \epsilon>$0.

Mer exakta uppskattningar kan byggas genom att skapa en sekvens med operatorer exponentiella så att fel villkoren avbryts.
Den enklaste formeln, den andra ordningen Trotter-Suzuki formel, tar formuläret $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ Right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ ett fel som kan göras mindre än $ \epsilon $ för alla $ \epsilon>$0 genom att välja $r $ för att skala som $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.

Även formler med högre ordning, särskilt ($ 2 $) för $k>$0 kan konstrueras rekursivt: $ $ U_ {2 000} (t) = [U_ {2} (s_k \~ t)] ^ 2 U_ {2 – 2} ([1-4s_k] t) [U_ {2-2} (S_K \~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2 000 + 1}/r ^ {2}), $ $ where $s _k = (4-4 ^ {1/(2 000-1)}) ^ {-1} $.

Det enklaste är följande fjärde ordning ($k = $2) formel, som ursprungligen introducerades av Suzuki: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5T ^ 5/r ^ 4), $ $ där $s _2 = (4-4 ^ {1/3}) ^ {-1} $.
I allmänhet kan godtyckliga formler med hög ordning skapas på samma sätt; kostnaderna för att använda mer komplexa integrerare uppväger dock ofta fördelarna bortom den fjärde ordningen för de flesta praktiska problemen.

För att se till att strategierna ovan fungerar måste vi ha en metod för att simulera en bred klass $e ^ {-iH_j t} $.
Den enklaste familjen av Hamiltonians och utan tvekan mest användbar, som vi kan använda här är Pauli-operatörer.
Pauli-operatörer kan enkelt simuleras eftersom de kan diagonalt med Clifford-åtgärder (som är standard grindar i Quantum Computing).
Efter att de har blivit diagonala kan deras Eigenvalues hittas genom att pariteten för de qubits som fungerar.

Till exempel $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {IT} & 0 \\\
        0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.
$ $ Här, $e ^ {-iHt} \ket {00} = e ^ {IT} \ket {00} $ och $e ^ {-iHt} \ket {01} = e ^ {-IT} \ket {01} $, som kan visas direkt till följd av det faktum att pariteten på $0 $ är $0 $ medan pariteten för bit strängen $1 $ är $1 $.

Exponenter för Pauli-operatörer kan implementeras direkt i Q# med hjälp av <xref:Microsoft.Quantum.Intrinsic.Exp> åtgärden:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

För Fermionic Hamiltonians mappar den [Jordanien-Wigner diskompositionen](xref:microsoft.quantum.chemistry.concepts.jordanwigner) enkelt in Hamiltonian i en summa av Pauli-operatörer.
Det innebär att ovanstående metod enkelt kan anpassas till att simulera kemi.
I stället för att manuellt loopa över alla Pauli-termer i Jordan-Wigner representation, är det ett enkelt exempel på hur en sådan simulering i kemi skulle se ut.
Vår start punkt är en [Jordanien – Wigner kodning](xref:microsoft.quantum.chemistry.concepts.jordanwigner) av Fermionic-Hamiltonian, uttryckt i kod som en instans av `JordanWignerEncoding` klassen.

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

Det här formatet på den Jordanien – Wigner-representation som används av Q# simulerings algoritmer är en användardefinierad typ `JordanWignerEncodingData` .
I Q# skickas det här formatet till en bekvämlighets funktion `TrotterStepOracle` som returnerar en operator som uppskattar tids utvecklingen med hjälp av Trotter – Suzuki Integrator, förutom andra parametrar som krävs för att köra den.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

För den här implementeringen används till exempel vissa optimeringar som diskuteras i [simuleringen av elektronisk struktur Hamiltonians med Quantum Computers](https://arxiv.org/abs/1001.3855) och [förbättrar Quantum-algoritmer för Quantum kemi](https://arxiv.org/abs/1403.1539) för att minimera antalet enskilda qubit-rotationer, samt minska simulerings fel.

## <a name="qubitization"></a>Qubitization

Qubitization är en alternativ metod för simulering som använder idéer från Quantum-instruktioner för att simulera Quantum Dynamics.
Medan qubitization kräver fler qubits än Trotter-formler, lovar metoden optimal skalning med utvecklings tiden och fel toleransen.
Därför har det blivit en prioriterad metod för att simulera Hamiltonian Dynamics i allmänhet och för att lösa det elektroniska struktur problemet i synnerhet.

På hög nivå uppnår qubitization detta genom följande steg.
Börja med att låta $H = \ sum_j h_j H_j $ för välHermitiane och $H _j $ och $h _j \ge $0.
Genom att utföra ett par av reflektioner implementerar qubitization en operator som motsvarar $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1)}, $ $ där $ | H | _1 = \ sum_j | h_j | $.
Nästa steg är att transformera Eigenvalues av en LED-operator från $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1)} $, där $E _k $ är Eigenvalues av $H $ till $e ^ {-iE_k t} $.
Detta kan uppnås med hjälp av en mängd olika metoder för att omvandla Quantum-värden, inklusive [bearbetning av Quantum-signaler](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

Alternativt, om bara statiska kvantiteter är önskade (t. ex. Hamiltonian), så räcker det att tillämpa [fas uppskattningen](xref:microsoft.quantum.libraries.characterization) direkt på $W $ för att beräkna mark tillståndets energi från resultatet genom att ta cosinus av resultatet.
Detta är viktigt eftersom det gör att Spectral-transformeringen kan utföras klassiskt i stället för att använda en metod för att omvandla en Quantum-värde.

På en mer detaljerad nivå kräver implementeringen av qubitization två under rutiner som tillhandahåller gränssnitten för Hamiltonian.
Till skillnad från Trotter – Suzuki-metoder är dessa underrutinerna Quantum inte för klassisk användning och implementeringen kommer att kräva att logarithmically fler qubits än skulle krävas för en Trotter-baserad simulering.

Den första Quantum-underrutinen som qubitization använder kallas $ \operatorname{Select} $ och det är lovat att ge \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} där varje $H _j $ antas vara Hermitian och enhetlig.
Även om det kan förefalla vara restriktivt, kom ihåg att Pauli-operatörerna är Hermitian och på samma sätt och att program som Quantum kemi-simulering i naturlig utsträckning omfattas av detta ramverk.
$ \Operatorname{Select} $-åtgärden, kanske överraskande, är i själva verket en reflektions åtgärd.
Detta kan ses från det faktum att $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $, eftersom varje $H _j $ är enhetlig och Hermitian och därför har Eigenvalues $ \pm $1.

Den andra subrutinen kallas $ \operatorname{Prepare} $.
Medan Select-åtgärden ger en enhetlig åtkomst till var och en av Hamiltonian termer $H _j $, ger en metod för att komma åt koefficienterna $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
\end{Equation}, med hjälp av en multiplicering-kontrollerad fas grind, ser vi att $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{Cases} \- \ket{x} & \text{IF} x = 0 \\\
        \ket{x} & \text{otherwise} \end{cases}.
$$

$ \Operatorname{prepare} $-åtgärden används inte direkt i qubitization, utan används i stället för att implementera en reflektion om det tillstånd som $ \operatorname{prepare} $ skapar $ $ \begin{align} R &amp; = 1-2 \ operatorname {prep} \ket {0} \bra {0} \operatorname{prepare} ^ {-1} \\ \\ &amp; = \operatorname{prepare} \Lambda \operatorname{prepare} ^ {-1} .
\end{align} $ $

Operatorn guida, $W $, kan uttryckas som $ \operatorname{Select} $ och $R $-åtgärder som $ $ W = \operatorname{Select} R, $ $ som återigen kan ses för att implementera en operatör som är likvärdig (upp till en isometry) att $e ^ {\pm i \cos ^ {-1} (H/| h | _1)} $.

Dessa under rutiner är enkla att konfigurera i Q# .
Som exempel bör du överväga den enkla qubit-Ising Hamiltonian där $H = X_1 + X_2 + Z_1 Z_2 $.
I det här fallet Q# anropas kod som implementerar åtgärden $ \operatorname{Select} $ av <xref:Microsoft.Quantum.Canon.MultiplexOperations> , medan $ \operatorname{prepare} $-åtgärden kan implementeras med hjälp av <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> .
Ett exempel som inbegriper simulering av Hubbard-modellen finns som ett [ Q# exempel](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).

Att manuellt ange dessa steg för valfria kemi-problem skulle kräva mycket ansträngning, vilket undviks med hjälp av kemi-biblioteket.
På samma sätt som för Trotter – Suzuki simulerings algoritmen ovan `JordanWignerEncodingData` skickas till den bekvämlighets funktion `QubitizationOracle` som returnerar den guidade operatorn, förutom andra parametrar som krävs för körningen.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Det är viktigt att implementeringen <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> gäller godtycklig Hamiltonians som anges som en linjär kombination av Pauli-strängar.
En version som är optimerad för kemi-simuleringar anropas med <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> .
Den här versionen är optimerad för att minimera antalet T-portar med hjälp av tekniker som beskrivs i [koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet](https://arxiv.org/abs/1805.03662).
