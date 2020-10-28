---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: Funktionen TimeDependentTrotterSimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730683"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="b7c78-102">Funktionen TimeDependentTrotterSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b7c78-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="b7c78-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b7c78-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b7c78-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7c78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7c78-105">`TimeDependentSimulationAlgorithm` funktion som använder en Trotter – Suzuki-dekomposition för att approximera en enhetlig operator som matchar tids beroende Schrodinger-ekvationen.</span><span class="sxs-lookup"><span data-stu-id="b7c78-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="b7c78-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b7c78-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="b7c78-107">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7c78-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7c78-108">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="b7c78-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="b7c78-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7c78-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7c78-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="b7c78-110">Order of Trotter integrator.</span></span> <span data-ttu-id="b7c78-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="b7c78-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="b7c78-112">Utdata: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="b7c78-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="b7c78-113">En `TimeDependentSimulationAlgorithm` typ.</span><span class="sxs-lookup"><span data-stu-id="b7c78-113">A `TimeDependentSimulationAlgorithm` type.</span></span>