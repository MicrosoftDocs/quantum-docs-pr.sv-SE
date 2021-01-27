---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Funktionen ControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840807"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="b8bb6-102">Funktionen ControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="b8bb6-102">ControlledOnBitString function</span></span>

<span data-ttu-id="b8bb6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b8bb6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b8bb6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8bb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8bb6-105">Returnerar en enhetlig åtgärd som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar en angiven bitmask.</span><span class="sxs-lookup"><span data-stu-id="b8bb6-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="b8bb6-106">Description</span><span class="sxs-lookup"><span data-stu-id="b8bb6-106">Description</span></span>

<span data-ttu-id="b8bb6-107">Resultatet av den här funktionen är en åtgärd som kan representeras av en enhetlig omvandling $U $ t. ex. \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{IF} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} där $V $ är en enhetlig omvandling som representerar åtgärdens åtgärd `oracle` .</span><span class="sxs-lookup"><span data-stu-id="b8bb6-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="b8bb6-108">Indata</span><span class="sxs-lookup"><span data-stu-id="b8bb6-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="b8bb6-109">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b8bb6-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b8bb6-110">Bit strängen som styr den åtgärd som åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="b8bb6-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="b8bb6-111">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="b8bb6-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b8bb6-112">Den enhetliga åtgärd som ska tillämpas på mål registret.</span><span class="sxs-lookup"><span data-stu-id="b8bb6-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="b8bb6-113">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="b8bb6-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b8bb6-114">En enhetlig åtgärd som gäller `oracle` för mål registret om status för kontroll registret motsvarar bitmask `bits` .</span><span class="sxs-lookup"><span data-stu-id="b8bb6-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b8bb6-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b8bb6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b8bb6-116">Inte</span><span class="sxs-lookup"><span data-stu-id="b8bb6-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="b8bb6-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="b8bb6-117">Example</span></span>

<span data-ttu-id="b8bb6-118">Följande kodfragment är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="b8bb6-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="b8bb6-119">och</span><span class="sxs-lookup"><span data-stu-id="b8bb6-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="b8bb6-120">Följande kod förbereder ett tillstånd $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:</span><span class="sxs-lookup"><span data-stu-id="b8bb6-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="b8bb6-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b8bb6-121">Remarks</span></span>

<span data-ttu-id="b8bb6-122">Mönstret som anges av `bits` kan vara kortare än `controlRegister` , och i så fall ignoreras ytterligare kontroll qubits (det vill säga varken kontrol leras på $ \ket {0} $ eller $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="b8bb6-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="b8bb6-123">Om `bits` är längre än `controlRegister` uppstår ett fel.</span><span class="sxs-lookup"><span data-stu-id="b8bb6-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="b8bb6-124">`bits` `oracle` Resultatet av den här funktionen är en åtgärd som utför följande steg för att få en boolesk matris och en enhetlig åtgärd:</span><span class="sxs-lookup"><span data-stu-id="b8bb6-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="b8bb6-125">tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` element i `bits` .</span><span class="sxs-lookup"><span data-stu-id="b8bb6-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="b8bb6-126">gäller `Controlled oracle` för kontroll-och mål registren.</span><span class="sxs-lookup"><span data-stu-id="b8bb6-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="b8bb6-127">tillämpa en `X` åtgärd på varje qubit i kontroll registret som motsvarar `false` elementet i `bits` igen för att returnera kontroll registret till det ursprungliga läget.</span><span class="sxs-lookup"><span data-stu-id="b8bb6-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="b8bb6-128">Utdata från `Controlled` Functor är ett specialfall av `ControlledOnBitString` var `bits` är lika med `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="b8bb6-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>