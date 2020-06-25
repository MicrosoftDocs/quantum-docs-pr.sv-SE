---
title: Bredd räknare
description: Lär dig mer om Microsoft QDK width-räknaren, som räknar antalet qubits som tilldelas och lånas ut av varje åtgärd i ett Quantum-program.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275566"
---
# <a name="width-counter"></a><span data-ttu-id="57ef6-103">Bredd räknare</span><span class="sxs-lookup"><span data-stu-id="57ef6-103">Width Counter</span></span>

<span data-ttu-id="57ef6-104">`Width Counter`Antalet qubits som tilldelas och lånas av varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="57ef6-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="57ef6-105">Alla åtgärder från `Microsoft.Quantum.Intrinsic` namn området uttrycks som enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="57ef6-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="57ef6-106">Några av de primitiva åtgärderna kan allokera extra qubits.</span><span class="sxs-lookup"><span data-stu-id="57ef6-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="57ef6-107">Du kan till exempel multiplicera kontrollerade `X` grindar eller kontrollerade `T` grindar.</span><span class="sxs-lookup"><span data-stu-id="57ef6-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="57ef6-108">Låt oss beräkna antalet extra qubits som allokerats av implementeringen av en multiplicering-kontrollerad `X` grind:</span><span class="sxs-lookup"><span data-stu-id="57ef6-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="57ef6-109">Använda en bredd räknare i ett C#-program</span><span class="sxs-lookup"><span data-stu-id="57ef6-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="57ef6-110">Multiplicering som styrs `X` på totalt 5 qubits kommer att allokera 2 hjälp qubits och dess ingångs bredd är 5.</span><span class="sxs-lookup"><span data-stu-id="57ef6-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="57ef6-111">Vi kan använda följande C#-program för att kontrol lera att detta är fallet:</span><span class="sxs-lookup"><span data-stu-id="57ef6-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="57ef6-112">Den första delen av programmet körs `ApplyMultiControlledX` .</span><span class="sxs-lookup"><span data-stu-id="57ef6-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="57ef6-113">I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet allokerade qubits samt antalet qubits som har kontroller ATS som inaktuella `X` .</span><span class="sxs-lookup"><span data-stu-id="57ef6-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="57ef6-114">Slutligen kan vi använda följande för att mata ut all statistik som samlas in med en bredd räknare i CSV-format:</span><span class="sxs-lookup"><span data-stu-id="57ef6-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="57ef6-115">Se även</span><span class="sxs-lookup"><span data-stu-id="57ef6-115">See also</span></span> ##

- <span data-ttu-id="57ef6-116">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="57ef6-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
