---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Funktionen CControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728872"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="01c90-102">Funktionen CControlledCA</span><span class="sxs-lookup"><span data-stu-id="01c90-102">CControlledCA function</span></span>

<span data-ttu-id="01c90-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01c90-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01c90-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01c90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01c90-105">Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann.</span><span class="sxs-lookup"><span data-stu-id="01c90-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="01c90-106">Om `false` händer ingenting.</span><span class="sxs-lookup"><span data-stu-id="01c90-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="01c90-107">Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="01c90-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="01c90-108">Indata</span><span class="sxs-lookup"><span data-stu-id="01c90-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="01c90-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="01c90-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="01c90-110">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="01c90-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="01c90-111">Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="01c90-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="01c90-112">En ny åtgärd som är OP om den klassiska kontroll biten är true.</span><span class="sxs-lookup"><span data-stu-id="01c90-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="01c90-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="01c90-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01c90-114">Inte</span><span class="sxs-lookup"><span data-stu-id="01c90-114">'T</span></span>

<span data-ttu-id="01c90-115">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="01c90-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="01c90-116">Se även</span><span class="sxs-lookup"><span data-stu-id="01c90-116">See Also</span></span>

- [<span data-ttu-id="01c90-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="01c90-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)