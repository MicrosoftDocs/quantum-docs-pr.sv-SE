---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: _JWOptimizedHpqTerm åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: b008315ded7cabc085e6d5da8f646e92914bf743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854815"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="85811-102">_JWOptimizedHpqTerm åtgärd</span><span class="sxs-lookup"><span data-stu-id="85811-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="85811-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="85811-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="85811-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="85811-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="85811-105">Använder tid-utveckling med en PQ-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="85811-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="85811-106">Indata</span><span class="sxs-lookup"><span data-stu-id="85811-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="85811-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="85811-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="85811-108">`GeneratorIndex` representerar en PQ-term.</span><span class="sxs-lookup"><span data-stu-id="85811-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="85811-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85811-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85811-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="85811-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="85811-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="85811-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="85811-112">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="85811-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="85811-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85811-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="85811-114">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="85811-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85811-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85811-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

