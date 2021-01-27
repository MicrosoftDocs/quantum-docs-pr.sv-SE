---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 8408dff24c5c57efbedb649ac182fac49e836a3e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850423"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="42689-102">ApplyToTailC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="42689-102">ApplyToTailC operation</span></span>

<span data-ttu-id="42689-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42689-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42689-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42689-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42689-105">Tillämpar en åtgärd på det sista elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="42689-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="42689-106">Description</span><span class="sxs-lookup"><span data-stu-id="42689-106">Description</span></span>

<span data-ttu-id="42689-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="42689-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="42689-108">Indata</span><span class="sxs-lookup"><span data-stu-id="42689-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="42689-109">OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="42689-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="42689-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="42689-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="42689-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="42689-111">targets : 'T[]</span></span>

<span data-ttu-id="42689-112">En matris med mål som den sista kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="42689-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42689-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42689-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42689-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="42689-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42689-115">Inte</span><span class="sxs-lookup"><span data-stu-id="42689-115">'T</span></span>

<span data-ttu-id="42689-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="42689-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="42689-117">Se även</span><span class="sxs-lookup"><span data-stu-id="42689-117">See Also</span></span>

- [<span data-ttu-id="42689-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="42689-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="42689-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="42689-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="42689-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="42689-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)