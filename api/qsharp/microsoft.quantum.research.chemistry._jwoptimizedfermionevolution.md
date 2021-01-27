---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 62fbd27f703a17a547d94e61c7a4981230a4b251
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854830"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="dfef2-102">_JWOptimizedFermionEvolution åtgärd</span><span class="sxs-lookup"><span data-stu-id="dfef2-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="dfef2-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dfef2-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="dfef2-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dfef2-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="dfef2-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JWOptimized-basen.</span><span class="sxs-lookup"><span data-stu-id="dfef2-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="dfef2-106">Mer information finns i [modeller för dynamisk Generator](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="dfef2-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dfef2-107">Indata</span><span class="sxs-lookup"><span data-stu-id="dfef2-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="dfef2-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="dfef2-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="dfef2-109">Ett Generator index som återges som en enhetlig utveckling i JWOptimized-basen.</span><span class="sxs-lookup"><span data-stu-id="dfef2-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="dfef2-110">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dfef2-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dfef2-111">En multiplikator vid tids åtgången för tids utveckling enligt den period som refereras i `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="dfef2-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="dfef2-112">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dfef2-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dfef2-113">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="dfef2-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="dfef2-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dfef2-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dfef2-115">Registrera dig efter tids utvecklings operatören.</span><span class="sxs-lookup"><span data-stu-id="dfef2-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dfef2-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dfef2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

