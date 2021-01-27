---
uid: Microsoft.Quantum.Logical.Not
title: Fungerar inte
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849081"
---
# <a name="not-function"></a><span data-ttu-id="1c8fe-102">Fungerar inte</span><span class="sxs-lookup"><span data-stu-id="1c8fe-102">Not function</span></span>

<span data-ttu-id="1c8fe-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1c8fe-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1c8fe-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c8fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c8fe-105">Returnerar den booleska negationen av ett värde.</span><span class="sxs-lookup"><span data-stu-id="1c8fe-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="1c8fe-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1c8fe-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="1c8fe-107">värde: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1c8fe-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1c8fe-108">Värdet som ska vara negationt.</span><span class="sxs-lookup"><span data-stu-id="1c8fe-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1c8fe-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1c8fe-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1c8fe-110">`true` om och bara om `value` är `false` .</span><span class="sxs-lookup"><span data-stu-id="1c8fe-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c8fe-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1c8fe-111">Remarks</span></span>

<span data-ttu-id="1c8fe-112">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="1c8fe-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```