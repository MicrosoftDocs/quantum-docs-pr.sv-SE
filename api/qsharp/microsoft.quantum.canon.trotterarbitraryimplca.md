---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728323"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="478dc-102">TrotterArbitraryImplCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="478dc-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="478dc-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="478dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="478dc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="478dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="478dc-105">Rekursiv implementering av jämnt Trotter – Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="478dc-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="478dc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="478dc-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="478dc-107">ordning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="478dc-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="478dc-108">Ordning på Trotter-Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="478dc-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="478dc-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="478dc-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="478dc-110">Antalet åtgärder som ska avgränsas i tids stegen.</span><span class="sxs-lookup"><span data-stu-id="478dc-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="478dc-111">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="478dc-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="478dc-112">En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) och ett Quantum-register (typ `'T` ) för dekomposition.</span><span class="sxs-lookup"><span data-stu-id="478dc-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="478dc-113">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="478dc-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="478dc-114">Multiplikator i storlek på varje steg i simuleringen.</span><span class="sxs-lookup"><span data-stu-id="478dc-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="478dc-115">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="478dc-115">target : 'T</span></span>

<span data-ttu-id="478dc-116">En Quantum-register där åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="478dc-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="478dc-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="478dc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="478dc-118">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="478dc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="478dc-119">Inte</span><span class="sxs-lookup"><span data-stu-id="478dc-119">'T</span></span>

<span data-ttu-id="478dc-120">Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="478dc-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>