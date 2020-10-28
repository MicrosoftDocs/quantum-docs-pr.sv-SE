---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732147"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="b4a25-102">ApplyBlockEncodingByLCU-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b4a25-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="b4a25-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b4a25-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b4a25-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4a25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4a25-105">Implementering av `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="b4a25-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a><span data-ttu-id="b4a25-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b4a25-106">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="b4a25-107">statePreparation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="b4a25-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="b4a25-108">väljare: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="b4a25-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="b4a25-109">hjälp: ' t</span><span class="sxs-lookup"><span data-stu-id="b4a25-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="b4a25-110">system: s</span><span class="sxs-lookup"><span data-stu-id="b4a25-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="b4a25-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4a25-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b4a25-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b4a25-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b4a25-113">Inte</span><span class="sxs-lookup"><span data-stu-id="b4a25-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="b4a25-114">Formulär</span><span class="sxs-lookup"><span data-stu-id="b4a25-114">'S</span></span>

