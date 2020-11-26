---
uid: Microsoft.Quantum.Canon.CControlledA
title: Funktionen CControlledA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: cb72ca5b3dab99b9ee8a994ba9fde46e0eae5594
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207521"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="08a03-102">Funktionen CControlledA</span><span class="sxs-lookup"><span data-stu-id="08a03-102">CControlledA function</span></span>

<span data-ttu-id="08a03-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="08a03-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="08a03-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08a03-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08a03-105">Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann.</span><span class="sxs-lookup"><span data-stu-id="08a03-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="08a03-106">Om `false` händer ingenting.</span><span class="sxs-lookup"><span data-stu-id="08a03-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="08a03-107">Modifieraren `A` anger att åtgärden är adjointable.</span><span class="sxs-lookup"><span data-stu-id="08a03-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="08a03-108">Indata</span><span class="sxs-lookup"><span data-stu-id="08a03-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="08a03-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="08a03-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="08a03-110">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="08a03-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="08a03-111">Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="08a03-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="08a03-112">En ny åtgärd som är OP om den klassiska kontroll biten är true.</span><span class="sxs-lookup"><span data-stu-id="08a03-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="08a03-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="08a03-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08a03-114">Inte</span><span class="sxs-lookup"><span data-stu-id="08a03-114">'T</span></span>

<span data-ttu-id="08a03-115">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="08a03-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="08a03-116">Se även</span><span class="sxs-lookup"><span data-stu-id="08a03-116">See Also</span></span>

- [<span data-ttu-id="08a03-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="08a03-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)