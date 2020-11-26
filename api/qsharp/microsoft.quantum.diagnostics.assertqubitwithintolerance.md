---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202200"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="b0fb7-102">AssertQubitWithinTolerance-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b0fb7-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="b0fb7-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b0fb7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b0fb7-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b0fb7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b0fb7-105">Förutsätter att qubit `q` finns i den förväntade eigenstate för Pauli Z-operatorn upp till en specifik tolerans.</span><span class="sxs-lookup"><span data-stu-id="b0fb7-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="b0fb7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b0fb7-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="b0fb7-107">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="b0fb7-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="b0fb7-108">Vilket tillstånd som qubit förväntas vara i: `Zero` eller `One` .</span><span class="sxs-lookup"><span data-stu-id="b0fb7-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="b0fb7-109">f: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b0fb7-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b0fb7-110">Qubit vars tillstånd är kontrollerad.</span><span class="sxs-lookup"><span data-stu-id="b0fb7-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b0fb7-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0fb7-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0fb7-112">Tolerans för sannolikheten för en mätning av qubit returnerar det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="b0fb7-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0fb7-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0fb7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0fb7-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b0fb7-114">Remarks</span></span>

<span data-ttu-id="b0fb7-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> gör det möjligt att kontrollera godtyckliga qubit i stället för att bara $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="b0fb7-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0fb7-116">Se även</span><span class="sxs-lookup"><span data-stu-id="b0fb7-116">See Also</span></span>

- [<span data-ttu-id="b0fb7-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="b0fb7-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)