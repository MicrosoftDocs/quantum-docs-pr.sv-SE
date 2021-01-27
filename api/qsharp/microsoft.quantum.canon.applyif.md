---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841874"
---
# <a name="applyif-operation"></a><span data-ttu-id="d2c12-102">ApplyIf-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d2c12-102">ApplyIf operation</span></span>

<span data-ttu-id="d2c12-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2c12-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2c12-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2c12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2c12-105">Tillämpar en åtgärd som villkoras på en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="d2c12-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="d2c12-106">Description</span><span class="sxs-lookup"><span data-stu-id="d2c12-106">Description</span></span>

<span data-ttu-id="d2c12-107">En åtgärd `op` och ett bit värde `bit` gäller `op` för `target` IF `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="d2c12-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="d2c12-108">Om `false` händer ingenting `target` .</span><span class="sxs-lookup"><span data-stu-id="d2c12-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="d2c12-109">Indata</span><span class="sxs-lookup"><span data-stu-id="d2c12-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d2c12-110">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2c12-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d2c12-111">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="d2c12-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="d2c12-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d2c12-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d2c12-113">ett booleskt värde som styr om OP används eller inte.</span><span class="sxs-lookup"><span data-stu-id="d2c12-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="d2c12-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="d2c12-114">target : 'T</span></span>

<span data-ttu-id="d2c12-115">De indatatyper som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="d2c12-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2c12-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2c12-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d2c12-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d2c12-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d2c12-118">Inte</span><span class="sxs-lookup"><span data-stu-id="d2c12-118">'T</span></span>

<span data-ttu-id="d2c12-119">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="d2c12-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="d2c12-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="d2c12-120">Example</span></span>

<span data-ttu-id="d2c12-121">Följande förbereder ett register över qubits till ett beräknings bas tillstånd som representeras av en klassisk bit sträng som anges som en matris med `Bool` värden:</span><span class="sxs-lookup"><span data-stu-id="d2c12-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="d2c12-122">Se även</span><span class="sxs-lookup"><span data-stu-id="d2c12-122">See Also</span></span>

- [<span data-ttu-id="d2c12-123">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="d2c12-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="d2c12-124">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="d2c12-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="d2c12-125">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="d2c12-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)