---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853443"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="493a3-102">AssertQubit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="493a3-102">AssertQubit operation</span></span>

<span data-ttu-id="493a3-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="493a3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="493a3-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="493a3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="493a3-105">Förutsätter att qubit `q` finns i den förväntade eigenstate för Pauli Z-operatorn.</span><span class="sxs-lookup"><span data-stu-id="493a3-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="493a3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="493a3-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="493a3-107">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="493a3-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="493a3-108">Vilket tillstånd som qubit förväntas vara i: `Zero` eller `One` .</span><span class="sxs-lookup"><span data-stu-id="493a3-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="493a3-109">f: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="493a3-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="493a3-110">Qubit vars tillstånd är kontrollerad.</span><span class="sxs-lookup"><span data-stu-id="493a3-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="493a3-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="493a3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="493a3-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="493a3-112">Remarks</span></span>

<span data-ttu-id="493a3-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> gör det möjligt att kontrollera godtyckliga qubit i stället för att bara $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="493a3-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="493a3-114">Se även</span><span class="sxs-lookup"><span data-stu-id="493a3-114">See Also</span></span>

- [<span data-ttu-id="493a3-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="493a3-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)