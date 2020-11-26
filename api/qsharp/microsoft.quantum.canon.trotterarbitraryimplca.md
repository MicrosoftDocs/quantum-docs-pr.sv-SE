---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204733"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="132f3-102">TrotterArbitraryImplCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="132f3-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="132f3-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="132f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="132f3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="132f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="132f3-105">Rekursiv implementering av jämnt Trotter – Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="132f3-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="132f3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="132f3-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="132f3-107">ordning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="132f3-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="132f3-108">Ordning på Trotter-Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="132f3-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="132f3-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="132f3-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="132f3-110">Antalet åtgärder som ska avgränsas i tids stegen.</span><span class="sxs-lookup"><span data-stu-id="132f3-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="132f3-111">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="132f3-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="132f3-112">En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) och ett Quantum-register (typ `'T` ) för dekomposition.</span><span class="sxs-lookup"><span data-stu-id="132f3-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="132f3-113">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="132f3-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="132f3-114">Multiplikator i storlek på varje steg i simuleringen.</span><span class="sxs-lookup"><span data-stu-id="132f3-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="132f3-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="132f3-115">target : 'T</span></span>

<span data-ttu-id="132f3-116">En Quantum-register där åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="132f3-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="132f3-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="132f3-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="132f3-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="132f3-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="132f3-119">Inte</span><span class="sxs-lookup"><span data-stu-id="132f3-119">'T</span></span>

<span data-ttu-id="132f3-120">Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="132f3-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>