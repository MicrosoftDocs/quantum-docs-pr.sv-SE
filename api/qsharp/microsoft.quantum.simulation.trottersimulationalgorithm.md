---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: Funktionen TrotterSimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730678"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="167ed-102">Funktionen TrotterSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="167ed-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="167ed-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="167ed-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="167ed-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="167ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="167ed-105">`SimulationAlgorithm` funktion som använder en Trotter – Suzuki-dekomposition för att uppskatta tids utvecklings operatorn _exp (-iHt)_ .</span><span class="sxs-lookup"><span data-stu-id="167ed-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="167ed-106">Indata</span><span class="sxs-lookup"><span data-stu-id="167ed-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="167ed-107">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="167ed-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="167ed-108">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="167ed-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="167ed-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="167ed-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="167ed-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="167ed-110">Order of Trotter integrator.</span></span> <span data-ttu-id="167ed-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="167ed-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="167ed-112">Utdata: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="167ed-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="167ed-113">En `SimulationAlgorithm` typ.</span><span class="sxs-lookup"><span data-stu-id="167ed-113">A `SimulationAlgorithm` type.</span></span>