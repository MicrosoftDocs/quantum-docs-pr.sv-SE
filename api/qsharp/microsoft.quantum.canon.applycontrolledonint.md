---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845105"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="c63c6-102">ApplyControlledOnInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c63c6-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="c63c6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c63c6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c63c6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c63c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c63c6-105">Använder en enhetlig åtgärd i mål registret om status för kontroll registret motsvarar ett angivet positivt heltal.</span><span class="sxs-lookup"><span data-stu-id="c63c6-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c63c6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c63c6-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="c63c6-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c63c6-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c63c6-108">Ett icke-negativt heltal som åtgärden `oracle` ska kontrol leras på.</span><span class="sxs-lookup"><span data-stu-id="c63c6-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="c63c6-109">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="c63c6-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c63c6-110">En enhetlig åtgärd som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="c63c6-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="c63c6-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c63c6-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c63c6-112">Ett Quantum-register som styr programmet för `oracle` .</span><span class="sxs-lookup"><span data-stu-id="c63c6-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="c63c6-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="c63c6-113">targetRegister : 'T</span></span>

<span data-ttu-id="c63c6-114">En register som ska tillämpas på `oracle` .</span><span class="sxs-lookup"><span data-stu-id="c63c6-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c63c6-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c63c6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c63c6-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c63c6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c63c6-117">Inte</span><span class="sxs-lookup"><span data-stu-id="c63c6-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c63c6-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c63c6-118">Remarks</span></span>

<span data-ttu-id="c63c6-119">Värdet för `numberState` tolkas med en lite-endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="c63c6-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="c63c6-120">`numberState` måste vara högst $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="c63c6-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="c63c6-121">Det kan till exempel `numberState = 537` `oracle` vara som tillämpas om och endast om `controlRegister` är i läget $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="c63c6-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>