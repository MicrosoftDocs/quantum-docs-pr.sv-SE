---
uid: Microsoft.Quantum.Canon.CurriedOp
title: Funktionen CurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216633"
---
# <a name="curriedop-function"></a><span data-ttu-id="06c8f-102">Funktionen CurriedOp</span><span class="sxs-lookup"><span data-stu-id="06c8f-102">CurriedOp function</span></span>

<span data-ttu-id="06c8f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06c8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06c8f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06c8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06c8f-105">Returnerar en Curried-version för en åtgärd på två indata.</span><span class="sxs-lookup"><span data-stu-id="06c8f-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="06c8f-106">Det vill säga en åtgärd med två indata, använder den här funktionen curry isomorphism $f (x, y) \equiv f (x) $ för att returnera en åtgärd av en indata som returnerar en åtgärd av en indata.</span><span class="sxs-lookup"><span data-stu-id="06c8f-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="06c8f-107">Indata</span><span class="sxs-lookup"><span data-stu-id="06c8f-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="06c8f-108">OP: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06c8f-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="06c8f-109">En åtgärd vars indatamängd är ett par.</span><span class="sxs-lookup"><span data-stu-id="06c8f-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="06c8f-110">Utdata: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06c8f-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="06c8f-111">En åtgärd som accepterar det första elementet i ett par och returnerar en åtgärd som accepterar den andra delen av den ursprungliga åtgärdens Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="06c8f-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06c8f-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="06c8f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06c8f-113">Inte</span><span class="sxs-lookup"><span data-stu-id="06c8f-113">'T</span></span>

<span data-ttu-id="06c8f-114">Typen för den första komponenten i en funktion som definieras i par.</span><span class="sxs-lookup"><span data-stu-id="06c8f-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="06c8f-115">' U</span><span class="sxs-lookup"><span data-stu-id="06c8f-115">'U</span></span>

<span data-ttu-id="06c8f-116">Typen för den andra komponenten i en funktion som definieras i par.</span><span class="sxs-lookup"><span data-stu-id="06c8f-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="06c8f-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="06c8f-117">Remarks</span></span>

<span data-ttu-id="06c8f-118">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="06c8f-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```