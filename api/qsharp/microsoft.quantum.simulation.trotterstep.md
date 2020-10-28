---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: Funktionen TrotterStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733990"
---
# <a name="trotterstep-function"></a><span data-ttu-id="1cd33-102">Funktionen TrotterStep</span><span class="sxs-lookup"><span data-stu-id="1cd33-102">TrotterStep function</span></span>

<span data-ttu-id="1cd33-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1cd33-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1cd33-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1cd33-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1cd33-105">Implementerar en enda tids period – steg-för-steg-utveckling enligt systemet som beskrivs i `EvolutionGenerator` använda en Trotter – Suzuki-dekomposition.</span><span class="sxs-lookup"><span data-stu-id="1cd33-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1cd33-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1cd33-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="1cd33-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="1cd33-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="1cd33-108">En fullständig beskrivning av systemet som ska simuleras.</span><span class="sxs-lookup"><span data-stu-id="1cd33-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="1cd33-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1cd33-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1cd33-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="1cd33-110">Order of Trotter integrator.</span></span> <span data-ttu-id="1cd33-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="1cd33-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="1cd33-112">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1cd33-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1cd33-113">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="1cd33-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="1cd33-114">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="1cd33-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1cd33-115">Enhetlig drift som uppskattar ett enda steg i tids utvecklingen för varaktighet `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="1cd33-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cd33-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1cd33-116">Remarks</span></span>

<span data-ttu-id="1cd33-117">Mer information om Trotter – Suzuki diskomposition finns i [Tidssorterad sammansättning](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="1cd33-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>