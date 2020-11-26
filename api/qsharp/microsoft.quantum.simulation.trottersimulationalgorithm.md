---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: Funktionen TrotterSimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: aa8338ab359441765db72a12f84a3a51e5bee3ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192544"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="1c30e-102">Funktionen TrotterSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="1c30e-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="1c30e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1c30e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1c30e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c30e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c30e-105">`SimulationAlgorithm` funktion som använder en Trotter – Suzuki-dekomposition för att uppskatta tids utvecklings operatorn _exp (-iHt)_.</span><span class="sxs-lookup"><span data-stu-id="1c30e-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="1c30e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1c30e-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="1c30e-107">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1c30e-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1c30e-108">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="1c30e-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="1c30e-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c30e-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c30e-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="1c30e-110">Order of Trotter integrator.</span></span> <span data-ttu-id="1c30e-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="1c30e-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="1c30e-112">Utdata: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="1c30e-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="1c30e-113">En `SimulationAlgorithm` typ.</span><span class="sxs-lookup"><span data-stu-id="1c30e-113">A `SimulationAlgorithm` type.</span></span>