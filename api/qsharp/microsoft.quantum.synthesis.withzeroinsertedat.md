---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Funktionen WithZeroInsertedAt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733878"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="da535-102">Funktionen WithZeroInsertedAt</span><span class="sxs-lookup"><span data-stu-id="da535-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="da535-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="da535-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="da535-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da535-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da535-105">Infoga en 0-bit i ett heltal</span><span class="sxs-lookup"><span data-stu-id="da535-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="da535-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="da535-106">Description</span></span>

<span data-ttu-id="da535-107">Den här åtgärden tar ett heltal, infogar en 0 vid bit `position` och returnerar det uppdaterade värdet som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="da535-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="da535-108">Om du till exempel infogar 0 vid position 2 i talet 10 (10 USD _ {10} = 1010_ {2} $) returnerar talet 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="da535-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="da535-109">Indata</span><span class="sxs-lookup"><span data-stu-id="da535-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="da535-110">position: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da535-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da535-111">Den position där 0 infogas</span><span class="sxs-lookup"><span data-stu-id="da535-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="da535-112">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da535-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da535-113">Värdet som ändras</span><span class="sxs-lookup"><span data-stu-id="da535-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="da535-114">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da535-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da535-115">Ändrat värde</span><span class="sxs-lookup"><span data-stu-id="da535-115">Modified value</span></span>