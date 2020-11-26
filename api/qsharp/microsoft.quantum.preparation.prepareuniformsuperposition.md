---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230097"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="6b3b7-102">PrepareUniformSuperposition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6b3b7-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="6b3b7-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6b3b7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6b3b7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b3b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b3b7-105">Skapar en enhetlig överplacering över tillstånd som kodar 0 till `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="6b3b7-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="6b3b7-106">Det vill säga den här enhetliga $U $ skapar en enhetlig överplacering över alla nummer tillstånd $0 $ till $M-$1, med ingångs tillstånd $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="6b3b7-107">Med andra ord, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="6b3b7-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6b3b7-109">Indata</span><span class="sxs-lookup"><span data-stu-id="6b3b7-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="6b3b7-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b3b7-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b3b7-111">Det önskade antalet tillstånd $M $ i enhetlig överposition.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="6b3b7-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6b3b7-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6b3b7-113">Qubit-registret som lagrar nummer tillstånden i `LittleEndian` formatet.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="6b3b7-114">Detta register måste kunna lagra numret $M-$1 och antas vara initierat i status $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b3b7-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b3b7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b3b7-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6b3b7-116">Remarks</span></span>

<span data-ttu-id="6b3b7-117">Åtgärden är adjointable men kräver att `indexRegister` är i ett enhetligt överplacerat tillstånd för de första `nIndices` bas tillstånden i detta fall.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>