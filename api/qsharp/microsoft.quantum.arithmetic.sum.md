---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Sum-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730438"
---
# <a name="sum-operation"></a><span data-ttu-id="4af4f-102">Sum-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4af4f-102">Sum operation</span></span>

<span data-ttu-id="4af4f-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4af4f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4af4f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4af4f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4af4f-105">Implementerar en omvänd sum-grind.</span><span class="sxs-lookup"><span data-stu-id="4af4f-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="4af4f-106">En driven bit som är kodad i qubit `carryIn` och två summand-bitar som är kodad i `summand1` och `summand2` , beräknar den bitvisa XOR `carryIn` `summand1` och `summand2` i qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="4af4f-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="4af4f-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4af4f-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="4af4f-108">transportera: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4af4f-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4af4f-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="4af4f-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="4af4f-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4af4f-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4af4f-111">Första summand-qubit.</span><span class="sxs-lookup"><span data-stu-id="4af4f-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="4af4f-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4af4f-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4af4f-113">Andra summand-qubit ersätts med den nedre biten av summan av `summand1` och `summand2` .</span><span class="sxs-lookup"><span data-stu-id="4af4f-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4af4f-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4af4f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4af4f-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4af4f-115">Remarks</span></span>

<span data-ttu-id="4af4f-116">I motsats till `Carry` åtgärden, beräknar detta inte den utgående biten.</span><span class="sxs-lookup"><span data-stu-id="4af4f-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>