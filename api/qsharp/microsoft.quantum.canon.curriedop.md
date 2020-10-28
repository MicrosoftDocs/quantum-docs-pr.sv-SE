---
uid: Microsoft.Quantum.Canon.CurriedOp
title: Funktionen CurriedOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728785"
---
# <a name="curriedop-function"></a><span data-ttu-id="7a617-102">Funktionen CurriedOp</span><span class="sxs-lookup"><span data-stu-id="7a617-102">CurriedOp function</span></span>

<span data-ttu-id="7a617-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a617-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a617-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a617-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a617-105">Returnerar en Curried-version för en åtgärd på två indata.</span><span class="sxs-lookup"><span data-stu-id="7a617-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="7a617-106">Det vill säga en åtgärd med två indata, använder den här funktionen curry isomorphism $f (x, y) \equiv f (x) $ för att returnera en åtgärd av en indata som returnerar en åtgärd av en indata.</span><span class="sxs-lookup"><span data-stu-id="7a617-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="7a617-107">Indata</span><span class="sxs-lookup"><span data-stu-id="7a617-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="7a617-108">OP: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a617-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7a617-109">En åtgärd vars indatamängd är ett par.</span><span class="sxs-lookup"><span data-stu-id="7a617-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="7a617-110">Utdata: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a617-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7a617-111">En åtgärd som accepterar det första elementet i ett par och returnerar en åtgärd som accepterar den andra delen av den ursprungliga åtgärdens Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="7a617-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7a617-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7a617-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a617-113">Inte</span><span class="sxs-lookup"><span data-stu-id="7a617-113">'T</span></span>

<span data-ttu-id="7a617-114">Typen för den första komponenten i en funktion som definieras i par.</span><span class="sxs-lookup"><span data-stu-id="7a617-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="7a617-115">' U</span><span class="sxs-lookup"><span data-stu-id="7a617-115">'U</span></span>

<span data-ttu-id="7a617-116">Typen för den andra komponenten i en funktion som definieras i par.</span><span class="sxs-lookup"><span data-stu-id="7a617-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a617-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7a617-117">Remarks</span></span>

<span data-ttu-id="7a617-118">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="7a617-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```