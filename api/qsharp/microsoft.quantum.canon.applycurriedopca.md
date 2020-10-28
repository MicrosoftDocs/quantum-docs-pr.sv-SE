---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: ApplyCurriedOpCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: 4e57772bc5440a473c28279ac125170caaa120f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729646"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="6979c-102">ApplyCurriedOpCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6979c-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="6979c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6979c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6979c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6979c-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="6979c-105">Indata</span><span class="sxs-lookup"><span data-stu-id="6979c-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="6979c-106">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just</span><span class="sxs-lookup"><span data-stu-id="6979c-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="6979c-107">första: ' t</span><span class="sxs-lookup"><span data-stu-id="6979c-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="6979c-108">sekund: ' U</span><span class="sxs-lookup"><span data-stu-id="6979c-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="6979c-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6979c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6979c-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6979c-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6979c-111">Inte</span><span class="sxs-lookup"><span data-stu-id="6979c-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="6979c-112">' U</span><span class="sxs-lookup"><span data-stu-id="6979c-112">'U</span></span>

