---
uid: Microsoft.Quantum.Canon.CControlledA
title: Funktionen CControlledA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728878"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="9d119-102">Funktionen CControlledA</span><span class="sxs-lookup"><span data-stu-id="9d119-102">CControlledA function</span></span>

<span data-ttu-id="9d119-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d119-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d119-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d119-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d119-105">Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann.</span><span class="sxs-lookup"><span data-stu-id="9d119-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="9d119-106">Om `false` händer ingenting.</span><span class="sxs-lookup"><span data-stu-id="9d119-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="9d119-107">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="9d119-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="9d119-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9d119-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="9d119-109">OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="9d119-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="9d119-110">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="9d119-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="9d119-111">Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="9d119-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="9d119-112">En ny åtgärd som är OP om den klassiska kontroll biten är true.</span><span class="sxs-lookup"><span data-stu-id="9d119-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9d119-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9d119-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9d119-114">Inte</span><span class="sxs-lookup"><span data-stu-id="9d119-114">'T</span></span>

<span data-ttu-id="9d119-115">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="9d119-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d119-116">Se även</span><span class="sxs-lookup"><span data-stu-id="9d119-116">See Also</span></span>

- [<span data-ttu-id="9d119-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="9d119-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)