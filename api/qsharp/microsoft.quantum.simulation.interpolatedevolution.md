---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Funktionen InterpolatedEvolution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726307"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="615a2-102">Funktionen InterpolatedEvolution</span><span class="sxs-lookup"><span data-stu-id="615a2-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="615a2-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="615a2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="615a2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="615a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="615a2-105">Interpolerar mellan två generatorer med ett enhetligt schema och returnerar en åtgärd som tillämpar simulerad utveckling under den resulterande tids beroende generatorn för en qubit-registrering.</span><span class="sxs-lookup"><span data-stu-id="615a2-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="615a2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="615a2-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="615a2-107">interpolationTime: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="615a2-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="615a2-108">Tid för att utföra interpolation över.</span><span class="sxs-lookup"><span data-stu-id="615a2-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="615a2-109">evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="615a2-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="615a2-110">Första generatorn för att simulera utvecklingen under.</span><span class="sxs-lookup"><span data-stu-id="615a2-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="615a2-111">evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="615a2-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="615a2-112">Slutlig generator för att simulera utveckling under.</span><span class="sxs-lookup"><span data-stu-id="615a2-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="615a2-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="615a2-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="615a2-114">En tids beroende simulerings algoritm som används för att simulera utvecklingen under det enhetliga sammanställnings schemat.</span><span class="sxs-lookup"><span data-stu-id="615a2-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="615a2-115">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="615a2-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="615a2-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="615a2-116">Remarks</span></span>

<span data-ttu-id="615a2-117">Om interpolsen har valts för att uppfylla adiabatic-villkoren returnerar den här funktionen en åtgärd som utför förberedelse av adiabatic-tillstånd för den slutliga dynamiska generatorn.</span><span class="sxs-lookup"><span data-stu-id="615a2-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>