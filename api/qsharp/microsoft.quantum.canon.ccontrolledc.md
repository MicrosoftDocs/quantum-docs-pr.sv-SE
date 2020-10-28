---
uid: Microsoft.Quantum.Canon.CControlledC
title: Funktionen CControlledC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728875"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="06ef2-102">Funktionen CControlledC</span><span class="sxs-lookup"><span data-stu-id="06ef2-102">CControlledC function</span></span>

<span data-ttu-id="06ef2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06ef2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06ef2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06ef2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06ef2-105">Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann.</span><span class="sxs-lookup"><span data-stu-id="06ef2-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="06ef2-106">Om `false` händer ingenting.</span><span class="sxs-lookup"><span data-stu-id="06ef2-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="06ef2-107">Modifieraren `C` anger att åtgärden är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="06ef2-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="06ef2-108">Indata</span><span class="sxs-lookup"><span data-stu-id="06ef2-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="06ef2-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="06ef2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="06ef2-110">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="06ef2-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="06ef2-111">Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="06ef2-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="06ef2-112">En ny åtgärd som är OP om den klassiska kontroll biten är true.</span><span class="sxs-lookup"><span data-stu-id="06ef2-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06ef2-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="06ef2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06ef2-114">Inte</span><span class="sxs-lookup"><span data-stu-id="06ef2-114">'T</span></span>

<span data-ttu-id="06ef2-115">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="06ef2-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="06ef2-116">Se även</span><span class="sxs-lookup"><span data-stu-id="06ef2-116">See Also</span></span>

- [<span data-ttu-id="06ef2-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="06ef2-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)