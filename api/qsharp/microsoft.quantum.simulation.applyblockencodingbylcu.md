---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225491"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="c2205-102">ApplyBlockEncodingByLCU-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c2205-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="c2205-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c2205-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c2205-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2205-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2205-105">Implementering av `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="c2205-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c2205-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c2205-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="c2205-107">statePreparation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="c2205-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="c2205-108">väljare: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="c2205-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="c2205-109">hjälp: ' t</span><span class="sxs-lookup"><span data-stu-id="c2205-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="c2205-110">system: s</span><span class="sxs-lookup"><span data-stu-id="c2205-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="c2205-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2205-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c2205-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c2205-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2205-113">Inte</span><span class="sxs-lookup"><span data-stu-id="c2205-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="c2205-114">Formulär</span><span class="sxs-lookup"><span data-stu-id="c2205-114">'S</span></span>

