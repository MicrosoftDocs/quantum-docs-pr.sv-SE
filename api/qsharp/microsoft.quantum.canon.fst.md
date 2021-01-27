---
uid: Microsoft.Quantum.Canon.Fst
title: Funktionen FST
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840520"
---
# <a name="fst-function"></a><span data-ttu-id="0f44d-102">Funktionen FST</span><span class="sxs-lookup"><span data-stu-id="0f44d-102">Fst function</span></span>

<span data-ttu-id="0f44d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f44d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f44d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f44d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f44d-105">Baserat på ett par, returnerar det första elementet.</span><span class="sxs-lookup"><span data-stu-id="0f44d-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="0f44d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0f44d-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="0f44d-107">par: (t. ex. ' U)</span><span class="sxs-lookup"><span data-stu-id="0f44d-107">pair : ('T,'U)</span></span>

<span data-ttu-id="0f44d-108">En tupel med två element.</span><span class="sxs-lookup"><span data-stu-id="0f44d-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="0f44d-109">Utdata: ' t</span><span class="sxs-lookup"><span data-stu-id="0f44d-109">Output : 'T</span></span>

<span data-ttu-id="0f44d-110">Det första elementet i `pair` .</span><span class="sxs-lookup"><span data-stu-id="0f44d-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f44d-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0f44d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f44d-112">Inte</span><span class="sxs-lookup"><span data-stu-id="0f44d-112">'T</span></span>

<span data-ttu-id="0f44d-113">Typ av parets första medlem.</span><span class="sxs-lookup"><span data-stu-id="0f44d-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="0f44d-114">' U</span><span class="sxs-lookup"><span data-stu-id="0f44d-114">'U</span></span>

<span data-ttu-id="0f44d-115">Typ av parets andra medlem.</span><span class="sxs-lookup"><span data-stu-id="0f44d-115">The type of the pair's second member.</span></span>