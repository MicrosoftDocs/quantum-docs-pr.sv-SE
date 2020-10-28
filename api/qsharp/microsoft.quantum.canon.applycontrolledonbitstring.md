---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729675"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="2aa6c-102">ApplyControlledOnBitString-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2aa6c-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="2aa6c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2aa6c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2aa6c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2aa6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2aa6c-105">Använder en enhetlig åtgärd i mål registret, som kontrol leras i ett tillstånd som anges av en viss bitmask.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="2aa6c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2aa6c-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="2aa6c-107">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2aa6c-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2aa6c-108">Bit strängen som styr den åtgärd som åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="2aa6c-109">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="2aa6c-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2aa6c-110">Den enhetliga åtgärd som ska tillämpas på mål registret.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="2aa6c-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2aa6c-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2aa6c-112">Ett Quantum-register som styr programmet för `oracle` .</span><span class="sxs-lookup"><span data-stu-id="2aa6c-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="2aa6c-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="2aa6c-113">targetRegister : 'T</span></span>

<span data-ttu-id="2aa6c-114">Mål registret som ska skickas till `oracle` som inmatade.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2aa6c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2aa6c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2aa6c-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2aa6c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2aa6c-117">Inte</span><span class="sxs-lookup"><span data-stu-id="2aa6c-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2aa6c-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2aa6c-118">Remarks</span></span>

<span data-ttu-id="2aa6c-119">Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="2aa6c-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="2aa6c-120">Om `bits` är längre än `controlRegister` uppstår ett fel.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="2aa6c-121">Det kan till exempel `bits = [0,1,0,0,1]` `oracle` vara som tillämpas om och endast om `controlRegister` är i läget $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>