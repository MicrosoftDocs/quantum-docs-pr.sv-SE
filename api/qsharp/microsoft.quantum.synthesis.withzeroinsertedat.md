---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Funktionen WithZeroInsertedAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855200"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="c5266-102">Funktionen WithZeroInsertedAt</span><span class="sxs-lookup"><span data-stu-id="c5266-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="c5266-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c5266-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c5266-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5266-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5266-105">Infoga en 0-bit i ett heltal</span><span class="sxs-lookup"><span data-stu-id="c5266-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="c5266-106">Description</span><span class="sxs-lookup"><span data-stu-id="c5266-106">Description</span></span>

<span data-ttu-id="c5266-107">Den här åtgärden tar ett heltal, infogar en 0 vid bit `position` och returnerar det uppdaterade värdet som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="c5266-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="c5266-108">Om du till exempel infogar 0 vid position 2 i talet 10 (10 USD _ {10} = 1010_ {2} $) returnerar talet 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="c5266-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="c5266-109">Indata</span><span class="sxs-lookup"><span data-stu-id="c5266-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="c5266-110">position: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5266-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5266-111">Den position där 0 infogas</span><span class="sxs-lookup"><span data-stu-id="c5266-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="c5266-112">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5266-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5266-113">Värdet som ändras</span><span class="sxs-lookup"><span data-stu-id="c5266-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="c5266-114">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5266-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5266-115">Ändrat värde</span><span class="sxs-lookup"><span data-stu-id="c5266-115">Modified value</span></span>