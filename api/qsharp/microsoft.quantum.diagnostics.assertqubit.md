---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727318"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="98f17-102">AssertQubit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="98f17-102">AssertQubit operation</span></span>

<span data-ttu-id="98f17-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="98f17-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="98f17-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98f17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98f17-105">Förutsätter att qubit `q` finns i den förväntade eigenstate för Pauli Z-operatorn.</span><span class="sxs-lookup"><span data-stu-id="98f17-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="98f17-106">Indata</span><span class="sxs-lookup"><span data-stu-id="98f17-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="98f17-107">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="98f17-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="98f17-108">Vilket tillstånd som qubit förväntas vara i: `Zero` eller `One` .</span><span class="sxs-lookup"><span data-stu-id="98f17-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="98f17-109">f: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="98f17-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="98f17-110">Qubit vars tillstånd är kontrollerad.</span><span class="sxs-lookup"><span data-stu-id="98f17-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98f17-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98f17-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="98f17-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="98f17-112">Remarks</span></span>

<span data-ttu-id="98f17-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> gör det möjligt att kontrollera godtyckliga qubit i stället för att bara $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="98f17-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="98f17-114">Se även</span><span class="sxs-lookup"><span data-stu-id="98f17-114">See Also</span></span>

- [<span data-ttu-id="98f17-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="98f17-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)