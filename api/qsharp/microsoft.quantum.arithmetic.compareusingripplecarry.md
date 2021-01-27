---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843293"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="7746a-102">CompareUsingRippleCarry-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7746a-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="7746a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7746a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7746a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7746a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7746a-105">Den här åtgärden testar om ett heltal som representeras av ett register över qubits är större än ett annat heltal, och använder en XOR av resultatet på en qubit.</span><span class="sxs-lookup"><span data-stu-id="7746a-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7746a-106">Description</span><span class="sxs-lookup"><span data-stu-id="7746a-106">Description</span></span>

<span data-ttu-id="7746a-107">`x` `y` Den här åtgärden kontrollerar om det finns två heltal och lagras i qubit-register med samma storlek `x > y` .</span><span class="sxs-lookup"><span data-stu-id="7746a-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="7746a-108">Om värdet är True är 1 XORed till en qubit för utdata.</span><span class="sxs-lookup"><span data-stu-id="7746a-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="7746a-109">Annars är 0 XORed till en qubit för utdata.</span><span class="sxs-lookup"><span data-stu-id="7746a-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="7746a-110">Med andra ord kan den här åtgärden representeras av den enhetliga $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="7746a-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="7746a-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7746a-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="7746a-112">Indata</span><span class="sxs-lookup"><span data-stu-id="7746a-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="7746a-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7746a-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7746a-114">Det första talet som ska jämföras lagrade i `LittleEndian` format i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="7746a-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="7746a-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7746a-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7746a-116">Det andra talet som ska jämföras lagrade i `LittleEndian` ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="7746a-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="7746a-117">utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7746a-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7746a-118">Qubit som lagrar resultatet av jämförelsen $x>y $.</span><span class="sxs-lookup"><span data-stu-id="7746a-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7746a-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7746a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="7746a-120">Referenser</span><span class="sxs-lookup"><span data-stu-id="7746a-120">References</span></span>

- <span data-ttu-id="7746a-121">En ny Quantum krusning-tillsatsering-krets Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="7746a-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>