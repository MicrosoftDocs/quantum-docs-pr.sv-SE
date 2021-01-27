---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: _JWOptimizedZZTerm åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: e12d146c0f706e960294580ad4b26ca83711ce33
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844359"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="bb1f7-102">_JWOptimizedZZTerm åtgärd</span><span class="sxs-lookup"><span data-stu-id="bb1f7-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="bb1f7-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bb1f7-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="bb1f7-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bb1f7-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="bb1f7-105">Använder tid-utveckling med en ZZ-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="bb1f7-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bb1f7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="bb1f7-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="bb1f7-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bb1f7-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bb1f7-108">`GeneratorIndex` representerar en ZZ-term.</span><span class="sxs-lookup"><span data-stu-id="bb1f7-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="bb1f7-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb1f7-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb1f7-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="bb1f7-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="bb1f7-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bb1f7-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bb1f7-112">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="bb1f7-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bb1f7-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bb1f7-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bb1f7-114">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="bb1f7-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb1f7-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb1f7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

