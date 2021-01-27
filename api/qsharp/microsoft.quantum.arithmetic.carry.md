---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Utföra åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843357"
---
# <a name="carry-operation"></a><span data-ttu-id="c3275-102">Utföra åtgärd</span><span class="sxs-lookup"><span data-stu-id="c3275-102">Carry operation</span></span>

<span data-ttu-id="c3275-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c3275-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c3275-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3275-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3275-105">Implementerar en omvänd bär grind.</span><span class="sxs-lookup"><span data-stu-id="c3275-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="c3275-106">En driven bit som är kodad i qubit `carryIn` och två summand-bitar som är kodad i `summand1` och `summand2` , beräknar den bitvisa XOR `carryIn` `summand1` och `summand2` i qubit `summand2` och XoReD till qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="c3275-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c3275-107">Indata</span><span class="sxs-lookup"><span data-stu-id="c3275-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="c3275-108">transportera: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c3275-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c3275-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="c3275-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="c3275-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c3275-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c3275-111">Första summand-qubit.</span><span class="sxs-lookup"><span data-stu-id="c3275-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="c3275-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c3275-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c3275-113">Andra summand-qubit ersätts med den nedre biten av summan av `summand1` och `summand2` .</span><span class="sxs-lookup"><span data-stu-id="c3275-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="c3275-114">över: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c3275-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c3275-115">Qubit, kommer att XoReD med den högre bit summan.</span><span class="sxs-lookup"><span data-stu-id="c3275-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3275-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3275-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

