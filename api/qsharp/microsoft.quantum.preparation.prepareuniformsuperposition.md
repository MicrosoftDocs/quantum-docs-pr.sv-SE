---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725824"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="d4c36-102">PrepareUniformSuperposition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d4c36-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="d4c36-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d4c36-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d4c36-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4c36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4c36-105">Skapar en enhetlig överplacering över tillstånd som kodar 0 till `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="d4c36-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="d4c36-106">Det vill säga den här enhetliga $U $ skapar en enhetlig överplacering över alla nummer tillstånd $0 $ till $M-$1, med ingångs tillstånd $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="d4c36-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="d4c36-107">Med andra ord, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="d4c36-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="d4c36-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="d4c36-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d4c36-109">Indata</span><span class="sxs-lookup"><span data-stu-id="d4c36-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="d4c36-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4c36-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4c36-111">Det önskade antalet tillstånd $M $ i enhetlig överposition.</span><span class="sxs-lookup"><span data-stu-id="d4c36-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="d4c36-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4c36-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d4c36-113">Qubit-registret som lagrar nummer tillstånden i `LittleEndian` formatet.</span><span class="sxs-lookup"><span data-stu-id="d4c36-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="d4c36-114">Detta register måste kunna lagra numret $M-$1 och antas vara initierat i status $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="d4c36-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4c36-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4c36-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d4c36-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d4c36-116">Remarks</span></span>

<span data-ttu-id="d4c36-117">Åtgärden är adjointable men kräver att `indexRegister` är i ett enhetligt överplacerat tillstånd för de första `nIndices` bas tillstånden i detta fall.</span><span class="sxs-lookup"><span data-stu-id="d4c36-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>