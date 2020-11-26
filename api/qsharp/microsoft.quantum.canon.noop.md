---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205974"
---
# <a name="noop-operation"></a><span data-ttu-id="18e67-102">NoOp-åtgärd</span><span class="sxs-lookup"><span data-stu-id="18e67-102">NoOp operation</span></span>

<span data-ttu-id="18e67-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="18e67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="18e67-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="18e67-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="18e67-105">Utför identitets åtgärden (inga-OP) i ett argument.</span><span class="sxs-lookup"><span data-stu-id="18e67-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="18e67-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="18e67-106">Description</span></span>

<span data-ttu-id="18e67-107">Den här åtgärden tar ett värde av valfri typ och gör ingenting.</span><span class="sxs-lookup"><span data-stu-id="18e67-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="18e67-108">Detta kan vara användbart när en indatatyp av en åtgärds typ förväntas, men ingen åtgärd vidtas.</span><span class="sxs-lookup"><span data-stu-id="18e67-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="18e67-109">Om till exempel en viss fel korrigering Syndrome anger att det inte har uppstått något fel, `NoOp<Qubit[]>` kan det vara rätt återställnings förfarande.</span><span class="sxs-lookup"><span data-stu-id="18e67-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="18e67-110">Om en åtgärd till exempel förväntar sig en tillstånds förberedelse procedur som inmatare, `NoOp<Qubit[]>` kan användas för att förbereda status $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="18e67-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="18e67-111">Indata</span><span class="sxs-lookup"><span data-stu-id="18e67-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="18e67-112">inmatade: ' t</span><span class="sxs-lookup"><span data-stu-id="18e67-112">input : 'T</span></span>

<span data-ttu-id="18e67-113">Ett värde som ska ignoreras.</span><span class="sxs-lookup"><span data-stu-id="18e67-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18e67-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18e67-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="18e67-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="18e67-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="18e67-116">Inte</span><span class="sxs-lookup"><span data-stu-id="18e67-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="18e67-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="18e67-117">Remarks</span></span>

<span data-ttu-id="18e67-118">I nästan alla fall måste typ parametern för `NoOp` anges explicit.</span><span class="sxs-lookup"><span data-stu-id="18e67-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="18e67-119">Är till exempel `NoOp<Qubit>` identiskt med <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="18e67-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="18e67-120">Se även</span><span class="sxs-lookup"><span data-stu-id="18e67-120">See Also</span></span>

- [<span data-ttu-id="18e67-121">Microsoft. Quantum. inbyggt.</span><span class="sxs-lookup"><span data-stu-id="18e67-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)