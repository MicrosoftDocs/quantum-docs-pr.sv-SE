---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Funktionen ComposedOutput
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728836"
---
# <a name="composedoutput-function"></a><span data-ttu-id="308a5-102">Funktionen ComposedOutput</span><span class="sxs-lookup"><span data-stu-id="308a5-102">ComposedOutput function</span></span>

<span data-ttu-id="308a5-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="308a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="308a5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="308a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="308a5-105">Returnerar utdata från sammansättningen av `inner` och `outer` för en specifik indata.</span><span class="sxs-lookup"><span data-stu-id="308a5-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="308a5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="308a5-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="308a5-107">yttre: "U->" V</span><span class="sxs-lookup"><span data-stu-id="308a5-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="308a5-108">inre: ' t-> ' U</span><span class="sxs-lookup"><span data-stu-id="308a5-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="308a5-109">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="308a5-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="308a5-110">Utdata: ' V</span><span class="sxs-lookup"><span data-stu-id="308a5-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="308a5-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="308a5-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="308a5-112">Inte</span><span class="sxs-lookup"><span data-stu-id="308a5-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="308a5-113">' U</span><span class="sxs-lookup"><span data-stu-id="308a5-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="308a5-114">' V</span><span class="sxs-lookup"><span data-stu-id="308a5-114">'V</span></span>

