---
title: Bredd räknare | Quantum Computer trace Simulator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442413"
---
# <a name="width-counter"></a><span data-ttu-id="79c91-103">Bredd räknare</span><span class="sxs-lookup"><span data-stu-id="79c91-103">Width Counter</span></span>

<span data-ttu-id="79c91-104">`Width Counter` räknar antalet allokerade och lånade av varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="79c91-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="79c91-105">Alla åtgärder från `Microsoft.Quantum.Primitive` namn området uttrycks i förhållande till enskilda qubit-rotationer, T-grindar, enkla qubit Clifford-portar, CNOT-portar och mätningar av multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="79c91-105">All operations from the `Microsoft.Quantum.Primitive` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="79c91-106">Några av de primitiva åtgärderna kan allokera extra qubits.</span><span class="sxs-lookup"><span data-stu-id="79c91-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="79c91-107">Du kan till exempel multiplicera kontrollerade `X` portar eller kontrollerade `T` portar.</span><span class="sxs-lookup"><span data-stu-id="79c91-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="79c91-108">Låt oss beräkna antalet extra qubits som allokerats av implementeringen av en multiplicering-kontrollerad `X`-grind:</span><span class="sxs-lookup"><span data-stu-id="79c91-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="79c91-109">Använda en bredd räknare i C# ett program</span><span class="sxs-lookup"><span data-stu-id="79c91-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="79c91-110">Om du multiplicerar kontrollerade `X` hur du får totalt 5 qubits allokeras 2 hjälp qubits och dess ingångs bredd är 5.</span><span class="sxs-lookup"><span data-stu-id="79c91-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="79c91-111">Vi kan använda följande C# program för att kontrol lera att detta är fallet:</span><span class="sxs-lookup"><span data-stu-id="79c91-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="79c91-112">Den första delen av programmet körs `MultiControlledXDriver`.</span><span class="sxs-lookup"><span data-stu-id="79c91-112">The first part of the program executes `MultiControlledXDriver`.</span></span> <span data-ttu-id="79c91-113">I den andra delen använder vi metoden `QCTraceSimulator.GetMetric` för att hämta antalet allokerade qubits samt antalet qubits som styrs `X` togs emot som inaktuella inmatade.</span><span class="sxs-lookup"><span data-stu-id="79c91-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="79c91-114">Slutligen kan vi använda följande för att mata ut all statistik som samlas in med en bredd räknare i CSV-format:</span><span class="sxs-lookup"><span data-stu-id="79c91-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="79c91-115">Se också</span><span class="sxs-lookup"><span data-stu-id="79c91-115">See also</span></span> ##

- <span data-ttu-id="79c91-116">Översikt över Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="79c91-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
