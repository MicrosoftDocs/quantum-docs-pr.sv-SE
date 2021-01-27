---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852814"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="5789b-102">ApplyBlockEncodingByLCU-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5789b-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="5789b-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5789b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5789b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5789b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5789b-105">Implementering av `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="5789b-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5789b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5789b-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="5789b-107">statePreparation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="5789b-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="5789b-108">väljare: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="5789b-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="5789b-109">hjälp: ' t</span><span class="sxs-lookup"><span data-stu-id="5789b-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="5789b-110">system: s</span><span class="sxs-lookup"><span data-stu-id="5789b-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="5789b-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5789b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5789b-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5789b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5789b-113">Inte</span><span class="sxs-lookup"><span data-stu-id="5789b-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="5789b-114">Formulär</span><span class="sxs-lookup"><span data-stu-id="5789b-114">'S</span></span>

