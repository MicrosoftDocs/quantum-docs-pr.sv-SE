---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845008"
---
# <a name="applyifca-operation"></a><span data-ttu-id="8af08-102">ApplyIfCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8af08-102">ApplyIfCA operation</span></span>

<span data-ttu-id="8af08-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8af08-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8af08-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8af08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8af08-105">Använder en enhetlig åtgärd som är villkorlig för en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="8af08-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8af08-106">Description</span><span class="sxs-lookup"><span data-stu-id="8af08-106">Description</span></span>

<span data-ttu-id="8af08-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8af08-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="8af08-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="8af08-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="8af08-109">Suffixet `CA` anger att åtgärden som ska tillämpas är enhetlig (kan kontrol leras och adjointable).</span><span class="sxs-lookup"><span data-stu-id="8af08-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="8af08-110">Indata</span><span class="sxs-lookup"><span data-stu-id="8af08-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="8af08-111">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="8af08-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8af08-112">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="8af08-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="8af08-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8af08-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8af08-114">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="8af08-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="8af08-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="8af08-115">target : 'T</span></span>

<span data-ttu-id="8af08-116">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="8af08-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8af08-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8af08-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8af08-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8af08-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8af08-119">Inte</span><span class="sxs-lookup"><span data-stu-id="8af08-119">'T</span></span>

<span data-ttu-id="8af08-120">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="8af08-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="8af08-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="8af08-121">Example</span></span>

<span data-ttu-id="8af08-122">Följande förbereder ett register över qubits till ett beräknings bas tillstånd som representeras av en klassisk bit sträng som anges som en matris med `Bool` värden:</span><span class="sxs-lookup"><span data-stu-id="8af08-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="8af08-123">Se även</span><span class="sxs-lookup"><span data-stu-id="8af08-123">See Also</span></span>

- [<span data-ttu-id="8af08-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="8af08-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="8af08-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="8af08-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="8af08-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="8af08-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)