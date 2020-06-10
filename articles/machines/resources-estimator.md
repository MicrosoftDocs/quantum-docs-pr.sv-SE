---
title: Resurs uppskattning för Quantum Development Kit-resurser
description: 'Lär dig mer om resurs uppskattningen som beräknar de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630138"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="e62e9-103">Mål datorn för resurs uppskattning</span><span class="sxs-lookup"><span data-stu-id="e62e9-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="e62e9-104">När namnet antyder `ResourcesEstimator` beräknar beräkningen de resurser som krävs för att köra en specifik instans av en Q #-åtgärd på en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="e62e9-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="e62e9-105">Detta åstadkommer detta genom att köra åtgärden Quantum utan att faktiskt simulera status för en Quantum-dator. av den anledningen kan IT uppskatta resurser för Q #-åtgärder som använder tusentals qubits, om den klassiska delen av koden kan köras på rimlig tid.</span><span class="sxs-lookup"><span data-stu-id="e62e9-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="e62e9-106">Användning</span><span class="sxs-lookup"><span data-stu-id="e62e9-106">Usage</span></span>

<span data-ttu-id="e62e9-107">`ResourcesEstimator`Är bara en annan typ av måldator, vilket innebär att den kan användas för att köra valfri Q #-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e62e9-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="e62e9-108">Som andra mål datorer ska du använda den på ett C#-värdprogram för att skapa en instans och skicka den som den första parametern för åtgärdens `Run` metod:</span><span class="sxs-lookup"><span data-stu-id="e62e9-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="e62e9-109">Som exemplet visar `ResourcesEstimator` tillhandahåller en `ToTSV()` metod för att skapa en tabell med Tabbavgränsade värden (TSV) som kan sparas i en fil eller som skrivs till konsolen för analys.</span><span class="sxs-lookup"><span data-stu-id="e62e9-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="e62e9-110">Resultatet av programmet ovan bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="e62e9-110">The output of the above program should look something like this:</span></span>

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="e62e9-111">I `ResourcesEstimator` återställs inte beräkningarna vid varje körning, om samma instans används för att köra en annan åtgärd, kommer den att behålla agg regeringar som räknas ovanpå befintliga resultat.</span><span class="sxs-lookup"><span data-stu-id="e62e9-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="e62e9-112">Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.</span><span class="sxs-lookup"><span data-stu-id="e62e9-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="e62e9-113">Hämta beräknade data program mässigt</span><span class="sxs-lookup"><span data-stu-id="e62e9-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="e62e9-114">Förutom en TSV-tabell kan de uppskattade resurserna hämtas via programmering via `ResourcesEstimator` `Data` egenskapen.</span><span class="sxs-lookup"><span data-stu-id="e62e9-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="e62e9-115">`Data`tillhandahåller en `System.DataTable` instans med två kolumner: `Metric` och `Sum` , indexerad av mått namnen.</span><span class="sxs-lookup"><span data-stu-id="e62e9-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="e62e9-116">Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford` `T` och portar som `CNOT` används av en Q #-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="e62e9-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="e62e9-117">Rapporterade mått</span><span class="sxs-lookup"><span data-stu-id="e62e9-117">Metrics Reported</span></span>

<span data-ttu-id="e62e9-118">Följande är en lista över mått som beräknas av `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="e62e9-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="e62e9-119">__CNOT__: antalet CNOT (kallas även för de kontrollerade Pauli X-grindarna) som körs.</span><span class="sxs-lookup"><span data-stu-id="e62e9-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="e62e9-120">__QubitClifford__: antalet enskilda qubit-Clifford och Pauli-portar som körs.</span><span class="sxs-lookup"><span data-stu-id="e62e9-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="e62e9-121">__Mått__: antalet utförda mätningar.</span><span class="sxs-lookup"><span data-stu-id="e62e9-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="e62e9-122">__R__: antalet enskilda qubit-rotationer som körs, med undantag för T-, Clifford-och Pauli-portar.</span><span class="sxs-lookup"><span data-stu-id="e62e9-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="e62e9-123">__T__: antalet t-grindar och deras konjugat, inklusive T-grind, T_x = H. T. H och T_y = hy. T. hy, körs.</span><span class="sxs-lookup"><span data-stu-id="e62e9-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="e62e9-124">__Djup__: djupet i Quantum-kretsen som körs av åtgärden Q #.</span><span class="sxs-lookup"><span data-stu-id="e62e9-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="e62e9-125">Som standard räknas bara T-portar i djupet. mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="e62e9-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="e62e9-126">__Width__: det högsta antalet qubits som tilldelas under körningen av Q #-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e62e9-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="e62e9-127">__BorrowedWidth__: det maximala antalet qubits som lånas inom Q #-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e62e9-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="e62e9-128">Ange sannolikheten för mätresultatet</span><span class="sxs-lookup"><span data-stu-id="e62e9-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="e62e9-129"><xref:microsoft.quantum.intrinsic.assertprob>från <xref:microsoft.quantum.intrinsic> namn området kan användas för att ge information om den förväntade sannolikheten för en mätning för att köra körningen av Q #-programmet.</span><span class="sxs-lookup"><span data-stu-id="e62e9-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="e62e9-130">Följande exempel illustrerar detta:</span><span class="sxs-lookup"><span data-stu-id="e62e9-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="e62e9-131">När de `ResourcesEstimator` påträffar `AssertProb` registreras det att mäta `PauliZ` `source` och `q` ska få ett resultat av `Zero` med sannolikhet 0,5.</span><span class="sxs-lookup"><span data-stu-id="e62e9-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="e62e9-132">När den körs `M` senare kommer den att hitta de registrerade värdena för resultatet sannolikhet och `M` returnerar `Zero` eller `One` med sannolikhet 0,5.</span><span class="sxs-lookup"><span data-stu-id="e62e9-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="e62e9-133">Se även</span><span class="sxs-lookup"><span data-stu-id="e62e9-133">See also</span></span>

<span data-ttu-id="e62e9-134">`ResourcesEstimator`Är byggd ovanpå dator [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro)från Quantum, som ger en mer omfattande uppsättning mått, möjlighet att rapportera mått för det fullständiga anrops diagrammet och funktioner som [distinkta inmatnings kontroll](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) för att hitta buggar i Q #-program.</span><span class="sxs-lookup"><span data-stu-id="e62e9-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="e62e9-135">Mer information finns i dokumentationen för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="e62e9-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

