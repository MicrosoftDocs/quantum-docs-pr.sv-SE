---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: Funktionen TimeDependentTrotterSimulationAlgorithm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858362"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="0977a-102">Funktionen TimeDependentTrotterSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="0977a-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="0977a-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0977a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0977a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0977a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0977a-105">`TimeDependentSimulationAlgorithm` funktion som använder en Trotter – Suzuki-dekomposition för att approximera en enhetlig operator som matchar tids beroende Schrodinger-ekvationen.</span><span class="sxs-lookup"><span data-stu-id="0977a-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="0977a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0977a-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="0977a-107">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0977a-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0977a-108">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="0977a-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="0977a-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0977a-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0977a-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="0977a-110">Order of Trotter integrator.</span></span> <span data-ttu-id="0977a-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="0977a-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="0977a-112">Utdata: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="0977a-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="0977a-113">En `TimeDependentSimulationAlgorithm` typ.</span><span class="sxs-lookup"><span data-stu-id="0977a-113">A `TimeDependentSimulationAlgorithm` type.</span></span>