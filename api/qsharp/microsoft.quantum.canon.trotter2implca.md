---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728332"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="3b29b-102">Trotter2ImplCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3b29b-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="3b29b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3b29b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3b29b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b29b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b29b-105">Implementering av den andra ordningen Trotter – Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="3b29b-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="3b29b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3b29b-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="3b29b-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b29b-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b29b-108">Antalet åtgärder som ska avgränsas i tids stegen.</span><span class="sxs-lookup"><span data-stu-id="3b29b-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="3b29b-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="3b29b-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="3b29b-110">En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) och ett Quantum-register (typ `'T` ) för dekomposition.</span><span class="sxs-lookup"><span data-stu-id="3b29b-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3b29b-111">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b29b-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b29b-112">Multiplikator i storlek på varje steg i simuleringen.</span><span class="sxs-lookup"><span data-stu-id="3b29b-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="3b29b-113">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="3b29b-113">target : 'T</span></span>

<span data-ttu-id="3b29b-114">En Quantum-register där åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="3b29b-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b29b-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b29b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3b29b-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3b29b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b29b-117">Inte</span><span class="sxs-lookup"><span data-stu-id="3b29b-117">'T</span></span>

<span data-ttu-id="3b29b-118">Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="3b29b-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>