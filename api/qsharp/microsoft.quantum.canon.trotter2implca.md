---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 0e3a7e53a4d415e6b5af81d9bb3f52cddf36c4b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204750"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="dac51-102">Trotter2ImplCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dac51-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="dac51-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dac51-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dac51-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dac51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dac51-105">Implementering av den andra ordningen Trotter – Suzuki Integrator.</span><span class="sxs-lookup"><span data-stu-id="dac51-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dac51-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dac51-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="dac51-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dac51-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dac51-108">Antalet åtgärder som ska avgränsas i tids stegen.</span><span class="sxs-lookup"><span data-stu-id="dac51-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="dac51-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="dac51-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dac51-110">En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) och ett Quantum-register (typ `'T` ) för dekomposition.</span><span class="sxs-lookup"><span data-stu-id="dac51-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="dac51-111">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dac51-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dac51-112">Multiplikator i storlek på varje steg i simuleringen.</span><span class="sxs-lookup"><span data-stu-id="dac51-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="dac51-113">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="dac51-113">target : 'T</span></span>

<span data-ttu-id="dac51-114">En Quantum-register där åtgärderna fungerar.</span><span class="sxs-lookup"><span data-stu-id="dac51-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dac51-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dac51-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dac51-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="dac51-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dac51-117">Inte</span><span class="sxs-lookup"><span data-stu-id="dac51-117">'T</span></span>

<span data-ttu-id="dac51-118">Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="dac51-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>