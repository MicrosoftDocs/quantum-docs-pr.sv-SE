---
uid: Microsoft.Quantum.Canon.Snd
title: SND-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728392"
---
# <a name="snd-function"></a><span data-ttu-id="8b7ac-102">SND-funktion</span><span class="sxs-lookup"><span data-stu-id="8b7ac-102">Snd function</span></span>

<span data-ttu-id="8b7ac-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b7ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b7ac-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b7ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b7ac-105">Ett annat element returneras av ett par.</span><span class="sxs-lookup"><span data-stu-id="8b7ac-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="8b7ac-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8b7ac-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="8b7ac-107">par: (t. ex. ' U)</span><span class="sxs-lookup"><span data-stu-id="8b7ac-107">pair : ('T,'U)</span></span>

<span data-ttu-id="8b7ac-108">En tupel med två element.</span><span class="sxs-lookup"><span data-stu-id="8b7ac-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="8b7ac-109">Utdata: ' U</span><span class="sxs-lookup"><span data-stu-id="8b7ac-109">Output : 'U</span></span>

<span data-ttu-id="8b7ac-110">Det andra elementet i `pair` .</span><span class="sxs-lookup"><span data-stu-id="8b7ac-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b7ac-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8b7ac-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b7ac-112">Inte</span><span class="sxs-lookup"><span data-stu-id="8b7ac-112">'T</span></span>

<span data-ttu-id="8b7ac-113">Typ av parets första medlem.</span><span class="sxs-lookup"><span data-stu-id="8b7ac-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="8b7ac-114">' U</span><span class="sxs-lookup"><span data-stu-id="8b7ac-114">'U</span></span>

<span data-ttu-id="8b7ac-115">Typ av parets andra medlem.</span><span class="sxs-lookup"><span data-stu-id="8b7ac-115">The type of the pair's second member.</span></span>