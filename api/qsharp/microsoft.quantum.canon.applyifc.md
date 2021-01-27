---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: ef16b23349b604d174e72d9ae06d2052e2ab60f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841866"
---
# <a name="applyifc-operation"></a><span data-ttu-id="ee238-102">ApplyIfC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ee238-102">ApplyIfC operation</span></span>

<span data-ttu-id="ee238-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee238-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee238-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee238-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee238-105">Använder en åtgärd som går att kontrol lera i en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="ee238-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="ee238-106">Description</span><span class="sxs-lookup"><span data-stu-id="ee238-106">Description</span></span>

<span data-ttu-id="ee238-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="ee238-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="ee238-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="ee238-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="ee238-109">Suffixet `C` anger att åtgärden som ska tillämpas är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="ee238-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="ee238-110">Indata</span><span class="sxs-lookup"><span data-stu-id="ee238-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="ee238-111">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="ee238-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ee238-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="ee238-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="ee238-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ee238-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ee238-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="ee238-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="ee238-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="ee238-115">target : 'T</span></span>

<span data-ttu-id="ee238-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ee238-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee238-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee238-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee238-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ee238-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee238-119">Inte</span><span class="sxs-lookup"><span data-stu-id="ee238-119">'T</span></span>

<span data-ttu-id="ee238-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="ee238-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="ee238-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="ee238-121">Example</span></span>

<span data-ttu-id="ee238-122">Följande förbereder ett register över qubits till ett beräknings bas tillstånd som representeras av en klassisk bit sträng som anges som en matris med `Bool` värden:</span><span class="sxs-lookup"><span data-stu-id="ee238-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="ee238-123">Se även</span><span class="sxs-lookup"><span data-stu-id="ee238-123">See Also</span></span>

- [<span data-ttu-id="ee238-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="ee238-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="ee238-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="ee238-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="ee238-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="ee238-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)