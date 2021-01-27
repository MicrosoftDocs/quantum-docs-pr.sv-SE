---
uid: Microsoft.Quantum.Canon.Snd
title: SND-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852158"
---
# <a name="snd-function"></a><span data-ttu-id="07084-102">SND-funktion</span><span class="sxs-lookup"><span data-stu-id="07084-102">Snd function</span></span>

<span data-ttu-id="07084-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="07084-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="07084-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07084-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07084-105">Ett annat element returneras av ett par.</span><span class="sxs-lookup"><span data-stu-id="07084-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="07084-106">Indata</span><span class="sxs-lookup"><span data-stu-id="07084-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="07084-107">par: (t. ex. ' U)</span><span class="sxs-lookup"><span data-stu-id="07084-107">pair : ('T,'U)</span></span>

<span data-ttu-id="07084-108">En tupel med två element.</span><span class="sxs-lookup"><span data-stu-id="07084-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="07084-109">Utdata: ' U</span><span class="sxs-lookup"><span data-stu-id="07084-109">Output : 'U</span></span>

<span data-ttu-id="07084-110">Det andra elementet i `pair` .</span><span class="sxs-lookup"><span data-stu-id="07084-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07084-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="07084-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="07084-112">Inte</span><span class="sxs-lookup"><span data-stu-id="07084-112">'T</span></span>

<span data-ttu-id="07084-113">Typ av parets första medlem.</span><span class="sxs-lookup"><span data-stu-id="07084-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="07084-114">' U</span><span class="sxs-lookup"><span data-stu-id="07084-114">'U</span></span>

<span data-ttu-id="07084-115">Typ av parets andra medlem.</span><span class="sxs-lookup"><span data-stu-id="07084-115">The type of the pair's second member.</span></span>