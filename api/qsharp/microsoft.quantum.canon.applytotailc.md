---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729043"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="f3dd1-102">ApplyToTailC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f3dd1-102">ApplyToTailC operation</span></span>

<span data-ttu-id="f3dd1-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f3dd1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f3dd1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3dd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3dd1-105">Tillämpar en åtgärd på det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="f3dd1-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f3dd1-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f3dd1-106">Description</span></span>

<span data-ttu-id="f3dd1-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f3dd1-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f3dd1-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f3dd1-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="f3dd1-109">OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f3dd1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f3dd1-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="f3dd1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f3dd1-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="f3dd1-111">targets : 'T[]</span></span>

<span data-ttu-id="f3dd1-112">En matris med mål som den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="f3dd1-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3dd1-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3dd1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f3dd1-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f3dd1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f3dd1-115">Inte</span><span class="sxs-lookup"><span data-stu-id="f3dd1-115">'T</span></span>

<span data-ttu-id="f3dd1-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="f3dd1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3dd1-117">Se även</span><span class="sxs-lookup"><span data-stu-id="f3dd1-117">See Also</span></span>

- [<span data-ttu-id="f3dd1-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="f3dd1-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="f3dd1-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="f3dd1-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="f3dd1-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="f3dd1-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)