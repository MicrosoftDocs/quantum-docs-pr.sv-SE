---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: Funktionen DecomposedIntoTimeStepsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728773"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="5d06a-102">Funktionen DecomposedIntoTimeStepsCA</span><span class="sxs-lookup"><span data-stu-id="5d06a-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="5d06a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5d06a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5d06a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d06a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d06a-105">Returnerar en åtgärd som implementerar Trotter – Suzuki Integrator för en specifik åtgärd.</span><span class="sxs-lookup"><span data-stu-id="5d06a-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="5d06a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5d06a-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="5d06a-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d06a-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d06a-108">Antalet åtgärder som ska avgränsas i tids stegen.</span><span class="sxs-lookup"><span data-stu-id="5d06a-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="5d06a-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="5d06a-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5d06a-110">En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) för dekomposition.</span><span class="sxs-lookup"><span data-stu-id="5d06a-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="5d06a-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d06a-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d06a-112">Väljer den ordning för Trotter – Suzuki Integrator som ska användas.</span><span class="sxs-lookup"><span data-stu-id="5d06a-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="5d06a-113">Order 1 och till och med order 2, 4, 6,... stöds för närvarande.</span><span class="sxs-lookup"><span data-stu-id="5d06a-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="5d06a-114">Utdata: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="5d06a-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5d06a-115">Returnerar en enhetlig implementering av Trotter – Suzuki Integrator, där den första parametern `Double` är integrations steg storleken, och den andra parametern är den som har agerat.</span><span class="sxs-lookup"><span data-stu-id="5d06a-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d06a-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5d06a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d06a-117">Inte</span><span class="sxs-lookup"><span data-stu-id="5d06a-117">'T</span></span>

<span data-ttu-id="5d06a-118">Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="5d06a-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d06a-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5d06a-119">Remarks</span></span>

<span data-ttu-id="5d06a-120">När `order` den här funktionen anropas med samma som `1` , returnerar den här funktionen en åtgärd som kan simuleras av den lägsta ordningen Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ där vi har följt notationen av [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) och låt $ \lambda $ vara utvecklings tiden (representeras av den returnerade åtgärdens första gång). och låt $ \{ H_j \} _ {j = 1} ^ {m} $ vara den uppsättning av dynamiska generatorer för (sned-Hermitian) som `op(j, lambda, _)` är integrerad som simuleras av den enhetliga operatorn $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="5d06a-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="5d06a-121">På samma sätt `order` returnerar en av `2` de andra ordningarna symmetrisk Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="5d06a-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="5d06a-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5d06a-122">\end{align} $$</span></span>

<span data-ttu-id="5d06a-123">Högre t.o.m. värden i `order` implementeras med hjälp av den rekursiva konstruktionen av [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="5d06a-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="5d06a-124">Referenser</span><span class="sxs-lookup"><span data-stu-id="5d06a-124">References</span></span>

- [<span data-ttu-id="5d06a-125">*D. W. bär, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="5d06a-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)