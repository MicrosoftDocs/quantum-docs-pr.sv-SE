---
uid: Microsoft.Quantum.Canon.Fst
title: Funktionen FST
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728707"
---
# <a name="fst-function"></a><span data-ttu-id="9cb79-102">Funktionen FST</span><span class="sxs-lookup"><span data-stu-id="9cb79-102">Fst function</span></span>

<span data-ttu-id="9cb79-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9cb79-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9cb79-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cb79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cb79-105">Baserat på ett par, returnerar det första elementet.</span><span class="sxs-lookup"><span data-stu-id="9cb79-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="9cb79-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9cb79-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="9cb79-107">par: (t. ex. ' U)</span><span class="sxs-lookup"><span data-stu-id="9cb79-107">pair : ('T,'U)</span></span>

<span data-ttu-id="9cb79-108">En tupel med två element.</span><span class="sxs-lookup"><span data-stu-id="9cb79-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="9cb79-109">Utdata: ' t</span><span class="sxs-lookup"><span data-stu-id="9cb79-109">Output : 'T</span></span>

<span data-ttu-id="9cb79-110">Det första elementet i `pair` .</span><span class="sxs-lookup"><span data-stu-id="9cb79-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9cb79-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9cb79-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9cb79-112">Inte</span><span class="sxs-lookup"><span data-stu-id="9cb79-112">'T</span></span>

<span data-ttu-id="9cb79-113">Typ av parets första medlem.</span><span class="sxs-lookup"><span data-stu-id="9cb79-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="9cb79-114">' U</span><span class="sxs-lookup"><span data-stu-id="9cb79-114">'U</span></span>

<span data-ttu-id="9cb79-115">Typ av parets andra medlem.</span><span class="sxs-lookup"><span data-stu-id="9cb79-115">The type of the pair's second member.</span></span>