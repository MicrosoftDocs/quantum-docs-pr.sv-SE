---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841268"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="70a49-102">ApplyToRestA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="70a49-102">ApplyToRestA operation</span></span>

<span data-ttu-id="70a49-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70a49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70a49-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70a49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70a49-105">Tillämpar en åtgärd på alla utom det första elementet i en matris.</span><span class="sxs-lookup"><span data-stu-id="70a49-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="70a49-106">Description</span><span class="sxs-lookup"><span data-stu-id="70a49-106">Description</span></span>

<span data-ttu-id="70a49-107">En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="70a49-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="70a49-108">Indata</span><span class="sxs-lookup"><span data-stu-id="70a49-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="70a49-109">OP: ' t [] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="70a49-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="70a49-110">En åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="70a49-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="70a49-111">mål: ' t []</span><span class="sxs-lookup"><span data-stu-id="70a49-111">targets : 'T[]</span></span>

<span data-ttu-id="70a49-112">En matris med mål, varav alla utom den första kommer att tillämpas på `op` .</span><span class="sxs-lookup"><span data-stu-id="70a49-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70a49-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70a49-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="70a49-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="70a49-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70a49-115">Inte</span><span class="sxs-lookup"><span data-stu-id="70a49-115">'T</span></span>

<span data-ttu-id="70a49-116">Indatatypen för den åtgärd som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="70a49-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="70a49-117">Se även</span><span class="sxs-lookup"><span data-stu-id="70a49-117">See Also</span></span>

- [<span data-ttu-id="70a49-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="70a49-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="70a49-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="70a49-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="70a49-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="70a49-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)