---
uid: Microsoft.Quantum.Logical.Not
title: Fungerar inte
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725998"
---
# <a name="not-function"></a><span data-ttu-id="a8088-102">Fungerar inte</span><span class="sxs-lookup"><span data-stu-id="a8088-102">Not function</span></span>

<span data-ttu-id="a8088-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a8088-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a8088-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8088-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8088-105">Returnerar den booleska negationen av ett värde.</span><span class="sxs-lookup"><span data-stu-id="a8088-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="a8088-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a8088-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="a8088-107">värde: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a8088-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a8088-108">Värdet som ska vara negationt.</span><span class="sxs-lookup"><span data-stu-id="a8088-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a8088-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a8088-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a8088-110">`true` om och bara om `value` är `false` .</span><span class="sxs-lookup"><span data-stu-id="a8088-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8088-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a8088-111">Remarks</span></span>

<span data-ttu-id="a8088-112">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="a8088-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```