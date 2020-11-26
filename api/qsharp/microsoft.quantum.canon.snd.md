---
uid: Microsoft.Quantum.Canon.Snd
title: SND-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205328"
---
# <a name="snd-function"></a><span data-ttu-id="7685c-102">SND-funktion</span><span class="sxs-lookup"><span data-stu-id="7685c-102">Snd function</span></span>

<span data-ttu-id="7685c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7685c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7685c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7685c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7685c-105">Ett annat element returneras av ett par.</span><span class="sxs-lookup"><span data-stu-id="7685c-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="7685c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7685c-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="7685c-107">par: (t. ex. ' U)</span><span class="sxs-lookup"><span data-stu-id="7685c-107">pair : ('T,'U)</span></span>

<span data-ttu-id="7685c-108">En tupel med två element.</span><span class="sxs-lookup"><span data-stu-id="7685c-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="7685c-109">Utdata: ' U</span><span class="sxs-lookup"><span data-stu-id="7685c-109">Output : 'U</span></span>

<span data-ttu-id="7685c-110">Det andra elementet i `pair` .</span><span class="sxs-lookup"><span data-stu-id="7685c-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7685c-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7685c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7685c-112">Inte</span><span class="sxs-lookup"><span data-stu-id="7685c-112">'T</span></span>

<span data-ttu-id="7685c-113">Typ av parets första medlem.</span><span class="sxs-lookup"><span data-stu-id="7685c-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="7685c-114">' U</span><span class="sxs-lookup"><span data-stu-id="7685c-114">'U</span></span>

<span data-ttu-id="7685c-115">Typ av parets andra medlem.</span><span class="sxs-lookup"><span data-stu-id="7685c-115">The type of the pair's second member.</span></span>