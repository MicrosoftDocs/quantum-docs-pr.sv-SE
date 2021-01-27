---
title: Bredd räknare – Quantum Development Kit
description: Lär dig mer om Microsoft QDK width-räknaren, som använder Quantum trace Simulator för att räkna antalet qubits som tilldelas och lånas av åtgärder i ett Q# program.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: e9a526ee1440544aace922bd83c6ea39cb83c1ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858584"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="36250-103">Quantum trace Simulator: bredd räknare</span><span class="sxs-lookup"><span data-stu-id="36250-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="36250-104">Bredd räknaren är en del av Quantum Development Kit [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="36250-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="36250-105">Du kan använda det för att räkna antalet qubits som tilldelas och lånas av varje åtgärd i ett Q# program.</span><span class="sxs-lookup"><span data-stu-id="36250-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="36250-106">Vissa primitiva åtgärder kan allokera extra qubits, till exempel multiplicera kontrollerade `X` åtgärder eller kontrollerade `T` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="36250-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="36250-107">Anropar bredd räknaren</span><span class="sxs-lookup"><span data-stu-id="36250-107">Invoking the width counter</span></span>

<span data-ttu-id="36250-108">Om du vill köra Quantum trace-simulatorn med bredd räknaren måste du skapa en <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instans, ställa in `UseWidthCounter` egenskapen på **True** och sedan skapa en ny <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instans med `QCTraceSimulatorConfiguration` som-parameter.</span><span class="sxs-lookup"><span data-stu-id="36250-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="36250-109">Använda bredd räknaren i ett C#-värd program</span><span class="sxs-lookup"><span data-stu-id="36250-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="36250-110">C#-exemplet som följer i det här avsnittet beräknar antalet extra qubits som allokerats av implementeringen av en <xref:Microsoft.Quantum.Intrinsic.X> utförd multiplicering-åtgärd, baserat på följande Q# exempel kod:</span><span class="sxs-lookup"><span data-stu-id="36250-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="36250-111">Den multiplicerade kontrollerade <xref:Microsoft.Quantum.Intrinsic.X> åtgärden fungerar på totalt fem qubits, allokerar två [Hjälp qubits](xref:microsoft.quantum.glossary#ancilla)och har en ingångs bredd på **5**.</span><span class="sxs-lookup"><span data-stu-id="36250-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="36250-112">Använd följande C#-program för att kontrol lera antalet:</span><span class="sxs-lookup"><span data-stu-id="36250-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="36250-113">Den första delen av programmet kör `ApplyMultiControlledX` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="36250-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="36250-114">I den andra delen används [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metoden för att hämta antalet allokerade qubits samt antalet qubits som `Controlled X` åtgärden tog emot som inmatade.</span><span class="sxs-lookup"><span data-stu-id="36250-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="36250-115">Slutligen kan du skriva ut all statistik som samlas in av bredd räknaren i CSV-format med följande:</span><span class="sxs-lookup"><span data-stu-id="36250-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="36250-116">Se även</span><span class="sxs-lookup"><span data-stu-id="36250-116">See also</span></span>

- <span data-ttu-id="36250-117">Översikt över Quantum Development Kit-verktyget för [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="36250-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="36250-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="36250-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="36250-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="36250-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="36250-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API-referensen.</span><span class="sxs-lookup"><span data-stu-id="36250-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
