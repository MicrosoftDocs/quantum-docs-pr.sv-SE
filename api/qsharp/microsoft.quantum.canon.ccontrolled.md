---
uid: Microsoft.Quantum.Canon.CControlled
title: Funktionen CControlled
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728881"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="05b2d-102">Funktionen CControlled</span><span class="sxs-lookup"><span data-stu-id="05b2d-102">CControlled function</span></span>

<span data-ttu-id="05b2d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05b2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05b2d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05b2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05b2d-105">Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann.</span><span class="sxs-lookup"><span data-stu-id="05b2d-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="05b2d-106">Om `false` händer ingenting.</span><span class="sxs-lookup"><span data-stu-id="05b2d-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="05b2d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="05b2d-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="05b2d-108">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05b2d-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="05b2d-109">En åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="05b2d-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="05b2d-110">Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05b2d-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="05b2d-111">En ny åtgärd som är OP om den klassiska kontroll biten är true.</span><span class="sxs-lookup"><span data-stu-id="05b2d-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="05b2d-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="05b2d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="05b2d-113">Inte</span><span class="sxs-lookup"><span data-stu-id="05b2d-113">'T</span></span>

<span data-ttu-id="05b2d-114">Indatatypen för den åtgärd som ska tillämpas villkorligt.</span><span class="sxs-lookup"><span data-stu-id="05b2d-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="05b2d-115">Se även</span><span class="sxs-lookup"><span data-stu-id="05b2d-115">See Also</span></span>

- [<span data-ttu-id="05b2d-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="05b2d-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="05b2d-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="05b2d-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="05b2d-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="05b2d-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)