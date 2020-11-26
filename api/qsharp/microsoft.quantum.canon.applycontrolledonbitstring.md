---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219081"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="06108-102">ApplyControlledOnBitString-åtgärd</span><span class="sxs-lookup"><span data-stu-id="06108-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="06108-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06108-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06108-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06108-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06108-105">Använder en enhetlig åtgärd i mål registret, som kontrol leras i ett tillstånd som anges av en viss bitmask.</span><span class="sxs-lookup"><span data-stu-id="06108-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="06108-106">Indata</span><span class="sxs-lookup"><span data-stu-id="06108-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="06108-107">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="06108-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="06108-108">Bit strängen som styr den åtgärd som åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="06108-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="06108-109">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="06108-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="06108-110">Den enhetliga åtgärd som ska tillämpas på mål registret.</span><span class="sxs-lookup"><span data-stu-id="06108-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="06108-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06108-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="06108-112">Ett Quantum-register som styr programmet för `oracle` .</span><span class="sxs-lookup"><span data-stu-id="06108-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="06108-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="06108-113">targetRegister : 'T</span></span>

<span data-ttu-id="06108-114">Mål registret som ska skickas till `oracle` som inmatade.</span><span class="sxs-lookup"><span data-stu-id="06108-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06108-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06108-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="06108-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="06108-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06108-117">Inte</span><span class="sxs-lookup"><span data-stu-id="06108-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="06108-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="06108-118">Remarks</span></span>

<span data-ttu-id="06108-119">Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="06108-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="06108-120">Om `bits` är längre än `controlRegister` uppstår ett fel.</span><span class="sxs-lookup"><span data-stu-id="06108-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="06108-121">Det kan till exempel `bits = [0,1,0,0,1]` `oracle` vara som tillämpas om och endast om `controlRegister` är i läget $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="06108-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>