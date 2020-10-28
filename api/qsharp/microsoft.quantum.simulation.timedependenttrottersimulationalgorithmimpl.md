---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730675"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="a31ef-102">TimeDependentTrotterSimulationAlgorithmImpl-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a31ef-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="a31ef-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a31ef-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a31ef-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a31ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a31ef-105">Implementering av flera Trotter-steg för att approximera en enhetlig operator som matchar tids beroende Schrödinger-ekvationen.</span><span class="sxs-lookup"><span data-stu-id="a31ef-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a31ef-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a31ef-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="a31ef-107">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a31ef-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a31ef-108">Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.</span><span class="sxs-lookup"><span data-stu-id="a31ef-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="a31ef-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a31ef-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a31ef-110">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="a31ef-110">Order of Trotter integrator.</span></span> <span data-ttu-id="a31ef-111">Det måste vara antingen 1 eller ett jämnt tal.</span><span class="sxs-lookup"><span data-stu-id="a31ef-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="a31ef-112">maxTime: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a31ef-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a31ef-113">Total varaktighet för simulering $t $.</span><span class="sxs-lookup"><span data-stu-id="a31ef-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="a31ef-114">evolutionSchedule: [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="a31ef-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="a31ef-115">En fullständig beskrivning av det tids beroende system som ska simuleras.</span><span class="sxs-lookup"><span data-stu-id="a31ef-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a31ef-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a31ef-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a31ef-117">Qubits har samarbetats av simuleringen.</span><span class="sxs-lookup"><span data-stu-id="a31ef-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a31ef-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a31ef-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

