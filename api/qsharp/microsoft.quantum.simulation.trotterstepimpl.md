---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 33dc922cd5a60590a1306369fb99615fc6575b22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856734"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="f55d8-102">TrotterStepImpl-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f55d8-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="f55d8-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f55d8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f55d8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f55d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f55d8-105">Implementerar tids utveckling med en term som finns i en `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="f55d8-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f55d8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f55d8-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="f55d8-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="f55d8-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="f55d8-108">En fullständig beskrivning av systemet som ska simuleras.</span><span class="sxs-lookup"><span data-stu-id="f55d8-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="f55d8-109">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f55d8-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f55d8-110">Heltals index till en term i det beskrivna systemet.</span><span class="sxs-lookup"><span data-stu-id="f55d8-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f55d8-111">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f55d8-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f55d8-112">Multiplikator i varaktighet för tids utveckling per term som indexeras av `idx` .</span><span class="sxs-lookup"><span data-stu-id="f55d8-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f55d8-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f55d8-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f55d8-114">Qubits har samarbetats av simuleringen.</span><span class="sxs-lookup"><span data-stu-id="f55d8-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f55d8-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f55d8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

