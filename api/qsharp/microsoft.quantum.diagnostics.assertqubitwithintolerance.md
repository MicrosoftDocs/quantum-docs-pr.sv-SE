---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727291"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="4f93e-102">AssertQubitWithinTolerance-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4f93e-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="4f93e-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4f93e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4f93e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f93e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f93e-105">Förutsätter att qubit `q` finns i den förväntade eigenstate för Pauli Z-operatorn upp till en specifik tolerans.</span><span class="sxs-lookup"><span data-stu-id="4f93e-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="4f93e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4f93e-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="4f93e-107">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="4f93e-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="4f93e-108">Vilket tillstånd som qubit förväntas vara i: `Zero` eller `One` .</span><span class="sxs-lookup"><span data-stu-id="4f93e-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="4f93e-109">f: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4f93e-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4f93e-110">Qubit vars tillstånd är kontrollerad.</span><span class="sxs-lookup"><span data-stu-id="4f93e-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="4f93e-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f93e-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f93e-112">Tolerans för sannolikheten för en mätning av qubit returnerar det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="4f93e-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f93e-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f93e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4f93e-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4f93e-114">Remarks</span></span>

<span data-ttu-id="4f93e-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> gör det möjligt att kontrollera godtyckliga qubit i stället för att bara $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="4f93e-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f93e-116">Se även</span><span class="sxs-lookup"><span data-stu-id="4f93e-116">See Also</span></span>

- [<span data-ttu-id="4f93e-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="4f93e-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)