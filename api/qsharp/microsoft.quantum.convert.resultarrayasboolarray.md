---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Funktionen ResultArrayAsBoolArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224232"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="cd4af-102">Funktionen ResultArrayAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="cd4af-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="cd4af-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="cd4af-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="cd4af-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd4af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd4af-105">Konverterar en `Result[]` typ till en `Bool[]` typ, där `One` mappas till `true` och `Zero` mappas till `false` .</span><span class="sxs-lookup"><span data-stu-id="cd4af-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="cd4af-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cd4af-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="cd4af-107">inmatade: __ogiltigt <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="cd4af-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="cd4af-108">`Result[]` som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="cd4af-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cd4af-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="cd4af-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="cd4af-110">En `Bool[]` som representerar `input` .</span><span class="sxs-lookup"><span data-stu-id="cd4af-110">A `Bool[]` representing the `input`.</span></span>