---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Funktionen ControlledOnBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216667"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="b593b-102">Funktionen ControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="b593b-102">ControlledOnBitString function</span></span>

<span data-ttu-id="b593b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b593b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b593b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b593b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b593b-105">Returnerar en enhetlig åtgärd som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar en angiven bitmask.</span><span class="sxs-lookup"><span data-stu-id="b593b-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="b593b-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b593b-106">Description</span></span>

<span data-ttu-id="b593b-107">Resultatet av den här funktionen är en åtgärd som kan representeras av en enhetlig omvandling $U $ t. ex. \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{IF} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} där $V $ är en enhetlig omvandling som representerar åtgärdens åtgärd `oracle` .</span><span class="sxs-lookup"><span data-stu-id="b593b-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="b593b-108">Indata</span><span class="sxs-lookup"><span data-stu-id="b593b-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="b593b-109">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b593b-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b593b-110">Bit strängen som styr den åtgärd som åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="b593b-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="b593b-111">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="b593b-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b593b-112">Den enhetliga åtgärd som ska tillämpas på mål registret.</span><span class="sxs-lookup"><span data-stu-id="b593b-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="b593b-113">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="b593b-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b593b-114">En enhetlig åtgärd som gäller `oracle` för mål registret om status för kontroll registret motsvarar bitmask `bits` .</span><span class="sxs-lookup"><span data-stu-id="b593b-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b593b-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b593b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b593b-116">Inte</span><span class="sxs-lookup"><span data-stu-id="b593b-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b593b-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b593b-117">Remarks</span></span>

<span data-ttu-id="b593b-118">Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="b593b-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="b593b-119">Om `bits` är längre än `controlRegister` uppstår ett fel.</span><span class="sxs-lookup"><span data-stu-id="b593b-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="b593b-120">`bits` `oracle` Resultatet av den här funktionen är en åtgärd som utför följande steg för att få en boolesk matris och en enhetlig åtgärd:</span><span class="sxs-lookup"><span data-stu-id="b593b-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="b593b-121">tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` element i `bits` .</span><span class="sxs-lookup"><span data-stu-id="b593b-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="b593b-122">gäller `Controlled oracle` för kontroll-och mål registren.</span><span class="sxs-lookup"><span data-stu-id="b593b-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="b593b-123">tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` elementet i `bits` igen för att returnera kontroll registret till det ursprungliga läget.</span><span class="sxs-lookup"><span data-stu-id="b593b-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="b593b-124">Utdata från `Controlled` Functor är ett specialfall av `ControlledOnBitString` var `bits` är lika med `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="b593b-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>