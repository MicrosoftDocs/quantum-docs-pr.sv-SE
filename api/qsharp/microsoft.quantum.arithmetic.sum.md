---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Sum-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847758"
---
# <a name="sum-operation"></a><span data-ttu-id="8ceda-102">Sum-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8ceda-102">Sum operation</span></span>

<span data-ttu-id="8ceda-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8ceda-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8ceda-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ceda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ceda-105">Implementerar en omvänd sum-grind.</span><span class="sxs-lookup"><span data-stu-id="8ceda-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="8ceda-106">En driven bit som är kodad i qubit `carryIn` och två summand-bitar som är kodad i `summand1` och `summand2` , beräknar den bitvisa XOR `carryIn` `summand1` och `summand2` i qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="8ceda-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8ceda-107">Indata</span><span class="sxs-lookup"><span data-stu-id="8ceda-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="8ceda-108">transportera: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ceda-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ceda-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="8ceda-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="8ceda-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ceda-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ceda-111">Första summand-qubit.</span><span class="sxs-lookup"><span data-stu-id="8ceda-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="8ceda-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ceda-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ceda-113">Andra summand-qubit ersätts med den nedre biten av summan av `summand1` och `summand2` .</span><span class="sxs-lookup"><span data-stu-id="8ceda-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ceda-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ceda-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8ceda-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8ceda-115">Remarks</span></span>

<span data-ttu-id="8ceda-116">I motsats till `Carry` åtgärden, beräknar detta inte den utgående biten.</span><span class="sxs-lookup"><span data-stu-id="8ceda-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>