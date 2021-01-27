---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846604"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="51a6f-102">IncrementByModularInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="51a6f-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="51a6f-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="51a6f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="51a6f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51a6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51a6f-105">Utför en modulär ökning av ett qubit-register med en heltalskonstant.</span><span class="sxs-lookup"><span data-stu-id="51a6f-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="51a6f-106">Description</span><span class="sxs-lookup"><span data-stu-id="51a6f-106">Description</span></span>

<span data-ttu-id="51a6f-107">Låt oss ange `increment` $a $, `modulus` genom att $N $ och Integer som är kodat i `target` $y $.</span><span class="sxs-lookup"><span data-stu-id="51a6f-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="51a6f-108">Åtgärden utför sedan följande omvandling: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} heltal kodas i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="51a6f-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="51a6f-109">Indata</span><span class="sxs-lookup"><span data-stu-id="51a6f-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="51a6f-110">ökning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="51a6f-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="51a6f-111">Heltals ökning $a $ som ska läggas till i $y $.</span><span class="sxs-lookup"><span data-stu-id="51a6f-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="51a6f-112">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="51a6f-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="51a6f-113">Integer $N $ som mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="51a6f-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="51a6f-114">mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="51a6f-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="51a6f-115">Integer $y $ i `LittleEndian` formatet som `increment` $a $ läggs till i.</span><span class="sxs-lookup"><span data-stu-id="51a6f-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="51a6f-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51a6f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="51a6f-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="51a6f-117">Remarks</span></span>

<span data-ttu-id="51a6f-118">Förutsätter att det initiala värdet för målet är mindre än $N $ och att ökningen $a $ är mindre än $N $.</span><span class="sxs-lookup"><span data-stu-id="51a6f-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="51a6f-119">Observera att <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementera samma åtgärd på `PhaseLittleEndian` grund av.</span><span class="sxs-lookup"><span data-stu-id="51a6f-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="51a6f-120">Se även</span><span class="sxs-lookup"><span data-stu-id="51a6f-120">See Also</span></span>

- [<span data-ttu-id="51a6f-121">Microsoft. Quantum. aritmetiska. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="51a6f-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)