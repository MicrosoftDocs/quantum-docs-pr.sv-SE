---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: Funktionen DecomposeIntoTimeStepsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728770"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="9ee2d-102">Funktionen DecomposeIntoTimeStepsCA</span><span class="sxs-lookup"><span data-stu-id="9ee2d-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="9ee2d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ee2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ee2d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ee2d-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="9ee2d-105">DecomposeIntoTimeStepsCA är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="9ee2d-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="9ee2d-106">Använd <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> i stället.</span><span class="sxs-lookup"><span data-stu-id="9ee2d-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9ee2d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="9ee2d-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="9ee2d-108">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ee2d-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="9ee2d-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="9ee2d-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="9ee2d-110">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ee2d-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="9ee2d-111">Utdata: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="9ee2d-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ee2d-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9ee2d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ee2d-113">Inte</span><span class="sxs-lookup"><span data-stu-id="9ee2d-113">'T</span></span>

