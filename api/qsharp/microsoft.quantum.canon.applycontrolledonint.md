---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729670"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="1c36c-102">ApplyControlledOnInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1c36c-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="1c36c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1c36c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1c36c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c36c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c36c-105">Använder en enhetlig åtgärd i mål registret om status för kontroll registret motsvarar ett angivet positivt heltal.</span><span class="sxs-lookup"><span data-stu-id="1c36c-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="1c36c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1c36c-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="1c36c-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c36c-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c36c-108">Ett icke-negativt heltal som åtgärden `oracle` ska kontrol leras på.</span><span class="sxs-lookup"><span data-stu-id="1c36c-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="1c36c-109">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="1c36c-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1c36c-110">En enhetlig åtgärd som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="1c36c-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="1c36c-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1c36c-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1c36c-112">Ett Quantum-register som styr programmet för `oracle` .</span><span class="sxs-lookup"><span data-stu-id="1c36c-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="1c36c-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="1c36c-113">targetRegister : 'T</span></span>

<span data-ttu-id="1c36c-114">En register som ska tillämpas på `oracle` .</span><span class="sxs-lookup"><span data-stu-id="1c36c-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c36c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c36c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1c36c-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1c36c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c36c-117">Inte</span><span class="sxs-lookup"><span data-stu-id="1c36c-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="1c36c-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1c36c-118">Remarks</span></span>

<span data-ttu-id="1c36c-119">Värdet för `numberState` tolkas med en lite-endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="1c36c-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="1c36c-120">`numberState` måste vara högst $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="1c36c-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="1c36c-121">Det kan till exempel `numberState = 537` `oracle` vara som tillämpas om och endast om `controlRegister` är i läget $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="1c36c-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>