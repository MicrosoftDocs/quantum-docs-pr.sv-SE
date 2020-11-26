---
uid: Microsoft.Quantum.Canon.Fst
title: Funktionen FST
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206943"
---
# <a name="fst-function"></a><span data-ttu-id="8d66b-102">Funktionen FST</span><span class="sxs-lookup"><span data-stu-id="8d66b-102">Fst function</span></span>

<span data-ttu-id="8d66b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d66b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d66b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d66b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d66b-105">Baserat på ett par, returnerar det första elementet.</span><span class="sxs-lookup"><span data-stu-id="8d66b-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="8d66b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8d66b-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="8d66b-107">par: (t. ex. ' U)</span><span class="sxs-lookup"><span data-stu-id="8d66b-107">pair : ('T,'U)</span></span>

<span data-ttu-id="8d66b-108">En tupel med två element.</span><span class="sxs-lookup"><span data-stu-id="8d66b-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="8d66b-109">Utdata: ' t</span><span class="sxs-lookup"><span data-stu-id="8d66b-109">Output : 'T</span></span>

<span data-ttu-id="8d66b-110">Det första elementet i `pair` .</span><span class="sxs-lookup"><span data-stu-id="8d66b-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8d66b-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8d66b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8d66b-112">Inte</span><span class="sxs-lookup"><span data-stu-id="8d66b-112">'T</span></span>

<span data-ttu-id="8d66b-113">Typ av parets första medlem.</span><span class="sxs-lookup"><span data-stu-id="8d66b-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="8d66b-114">' U</span><span class="sxs-lookup"><span data-stu-id="8d66b-114">'U</span></span>

<span data-ttu-id="8d66b-115">Typ av parets andra medlem.</span><span class="sxs-lookup"><span data-stu-id="8d66b-115">The type of the pair's second member.</span></span>