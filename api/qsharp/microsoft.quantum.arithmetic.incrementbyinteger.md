---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843160"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="14c37-102">IncrementByInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="14c37-102">IncrementByInteger operation</span></span>

<span data-ttu-id="14c37-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="14c37-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="14c37-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14c37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14c37-105">Ökar en osignerad Quantum-registrering med ett klassiskt heltal med hjälp av fas rotationer.</span><span class="sxs-lookup"><span data-stu-id="14c37-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="14c37-106">Description</span><span class="sxs-lookup"><span data-stu-id="14c37-106">Description</span></span>

<span data-ttu-id="14c37-107">Anta att `target` koda ett osignerat heltal $x $ i en lite-endian-kodning och att det `increment` motsvarar $a $.</span><span class="sxs-lookup"><span data-stu-id="14c37-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="14c37-108">Den här åtgärden implementerar sedan den enhetliga $ \ket{x} \mapsto \ket{x + a} $, där additionen utförs med modulo $2 ^ n $, där $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="14c37-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="14c37-109">Indata</span><span class="sxs-lookup"><span data-stu-id="14c37-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="14c37-110">ökning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="14c37-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="14c37-111">Det heltal som `target` ökar med.</span><span class="sxs-lookup"><span data-stu-id="14c37-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="14c37-112">mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="14c37-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="14c37-113">Ett Quantum-register som kodar ett osignerat heltal med lite-endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="14c37-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14c37-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14c37-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

