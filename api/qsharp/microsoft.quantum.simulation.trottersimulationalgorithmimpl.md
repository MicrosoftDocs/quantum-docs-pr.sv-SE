---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733995"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="a5e98-102">TrotterSimulationAlgorithmImpl-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a5e98-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="a5e98-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a5e98-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a5e98-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5e98-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5e98-105">Gör upprepade anrop till `TrotterStep` att uppskatta tids utvecklings operatorn exp ( _-iHt_ ).</span><span class="sxs-lookup"><span data-stu-id="a5e98-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a5e98-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a5e98-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="a5e98-107">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5e98-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5e98-108">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="a5e98-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="a5e98-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5e98-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5e98-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="a5e98-110">Order of Trotter integrator.</span></span> <span data-ttu-id="a5e98-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="a5e98-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="a5e98-112">maxTime: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5e98-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5e98-113">Total varaktighet för simulering $t $.</span><span class="sxs-lookup"><span data-stu-id="a5e98-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="a5e98-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="a5e98-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="a5e98-115">En fullständig beskrivning av systemet som ska simuleras.</span><span class="sxs-lookup"><span data-stu-id="a5e98-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a5e98-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5e98-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5e98-117">Qubits har samarbetats av simuleringen.</span><span class="sxs-lookup"><span data-stu-id="a5e98-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5e98-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5e98-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

