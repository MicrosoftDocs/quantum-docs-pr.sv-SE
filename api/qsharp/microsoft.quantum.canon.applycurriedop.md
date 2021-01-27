---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841920"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="fc145-102">ApplyCurriedOp-åtgärd</span><span class="sxs-lookup"><span data-stu-id="fc145-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="fc145-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc145-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc145-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc145-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="fc145-105">Indata</span><span class="sxs-lookup"><span data-stu-id="fc145-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="fc145-106">curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc145-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="fc145-107">första: ' t</span><span class="sxs-lookup"><span data-stu-id="fc145-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="fc145-108">sekund: ' U</span><span class="sxs-lookup"><span data-stu-id="fc145-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="fc145-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc145-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fc145-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="fc145-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc145-111">Inte</span><span class="sxs-lookup"><span data-stu-id="fc145-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="fc145-112">' U</span><span class="sxs-lookup"><span data-stu-id="fc145-112">'U</span></span>

