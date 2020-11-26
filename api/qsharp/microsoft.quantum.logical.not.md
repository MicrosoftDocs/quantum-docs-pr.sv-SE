---
uid: Microsoft.Quantum.Logical.Not
title: Fungerar inte
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197457"
---
# <a name="not-function"></a><span data-ttu-id="36338-102">Fungerar inte</span><span class="sxs-lookup"><span data-stu-id="36338-102">Not function</span></span>

<span data-ttu-id="36338-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="36338-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="36338-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36338-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36338-105">Returnerar den booleska negationen av ett värde.</span><span class="sxs-lookup"><span data-stu-id="36338-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="36338-106">Indata</span><span class="sxs-lookup"><span data-stu-id="36338-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="36338-107">värde: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="36338-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="36338-108">Värdet som ska vara negationt.</span><span class="sxs-lookup"><span data-stu-id="36338-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="36338-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="36338-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="36338-110">`true` om och bara om `value` är `false` .</span><span class="sxs-lookup"><span data-stu-id="36338-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36338-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="36338-111">Remarks</span></span>

<span data-ttu-id="36338-112">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="36338-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```