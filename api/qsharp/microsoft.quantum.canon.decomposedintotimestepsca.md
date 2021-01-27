---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: Funktionen DecomposedIntoTimeStepsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840693"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="d8e06-102">Funktionen DecomposedIntoTimeStepsCA</span><span class="sxs-lookup"><span data-stu-id="d8e06-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="d8e06-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8e06-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8e06-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8e06-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8e06-105">Returnerar en åtgärd som implementerar Trotter – Suzuki Integrator för en specifik åtgärd.</span><span class="sxs-lookup"><span data-stu-id="d8e06-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d8e06-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d8e06-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="d8e06-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8e06-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8e06-108">Antalet åtgärder som ska avgränsas i tids stegen.</span><span class="sxs-lookup"><span data-stu-id="d8e06-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="d8e06-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="d8e06-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d8e06-110">En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) för dekomposition.</span><span class="sxs-lookup"><span data-stu-id="d8e06-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="d8e06-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8e06-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8e06-112">Väljer den ordning för Trotter – Suzuki Integrator som ska användas.</span><span class="sxs-lookup"><span data-stu-id="d8e06-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="d8e06-113">Order 1 och till och med order 2, 4, 6,... stöds för närvarande.</span><span class="sxs-lookup"><span data-stu-id="d8e06-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="d8e06-114">Utdata: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="d8e06-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d8e06-115">Returnerar en enhetlig implementering av Trotter – Suzuki Integrator, där den första parametern `Double` är integrations steg storleken, och den andra parametern är den som har agerat.</span><span class="sxs-lookup"><span data-stu-id="d8e06-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d8e06-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d8e06-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8e06-117">Inte</span><span class="sxs-lookup"><span data-stu-id="d8e06-117">'T</span></span>

<span data-ttu-id="d8e06-118">Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="d8e06-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8e06-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d8e06-119">Remarks</span></span>

<span data-ttu-id="d8e06-120">När `order` den här funktionen anropas med samma som `1` , returnerar den här funktionen en åtgärd som kan simuleras av den lägsta ordningen Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ där vi har följt notationen av [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) och låt $ \lambda $ vara utvecklings tiden (representeras av den returnerade åtgärdens första gång). och låt $ \{ H_j \} _ {j = 1} ^ {m} $ vara den uppsättning av dynamiska generatorer för (sned-Hermitian) som `op(j, lambda, _)` är integrerad som simuleras av den enhetliga operatorn $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="d8e06-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="d8e06-121">På samma sätt `order` returnerar en av `2` de andra ordningarna symmetrisk Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="d8e06-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="d8e06-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d8e06-122">\end{align} $$</span></span>

<span data-ttu-id="d8e06-123">Högre t.o.m. värden i `order` implementeras med hjälp av den rekursiva konstruktionen av [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="d8e06-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="d8e06-124">Referenser</span><span class="sxs-lookup"><span data-stu-id="d8e06-124">References</span></span>

- [<span data-ttu-id="d8e06-125">*D. W. bär, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="d8e06-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)