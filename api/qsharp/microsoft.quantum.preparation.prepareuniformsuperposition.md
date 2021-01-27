---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854324"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="f4a9a-102">PrepareUniformSuperposition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f4a9a-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="f4a9a-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f4a9a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f4a9a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4a9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4a9a-105">Skapar en enhetlig överplacering över tillstånd som kodar 0 till `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="f4a9a-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="f4a9a-106">Det vill säga den här enhetliga $U $ skapar en enhetlig överplacering över alla nummer tillstånd $0 $ till $M-$1, med ingångs tillstånd $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="f4a9a-107">Med andra ord, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="f4a9a-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f4a9a-109">Indata</span><span class="sxs-lookup"><span data-stu-id="f4a9a-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="f4a9a-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4a9a-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4a9a-111">Det önskade antalet tillstånd $M $ i enhetlig överposition.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="f4a9a-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f4a9a-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f4a9a-113">Qubit-registret som lagrar nummer tillstånden i `LittleEndian` formatet.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="f4a9a-114">Detta register måste kunna lagra numret $M-$1 och antas vara initierat i status $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4a9a-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4a9a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f4a9a-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="f4a9a-116">Example</span></span>

<span data-ttu-id="f4a9a-117">I följande exempel förbereds tillstånd $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $ på $3 $ qubits.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-117">The following example prepares the state $\frac{1}{\sqrt{6}}\sum_{j=0}^{5}\ket{j}$ on $3$ qubits.</span></span>

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a><span data-ttu-id="f4a9a-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f4a9a-118">Remarks</span></span>

<span data-ttu-id="f4a9a-119">Åtgärden är adjointable men kräver att `indexRegister` är i ett enhetligt överplacerat tillstånd för de första `nIndices` bas tillstånden i detta fall.</span><span class="sxs-lookup"><span data-stu-id="f4a9a-119">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>