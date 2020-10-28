---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: Funktionen LessThanLexographic
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726040"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="fb931-102">Funktionen LessThanLexographic</span><span class="sxs-lookup"><span data-stu-id="fb931-102">LessThanLexographic function</span></span>

<span data-ttu-id="fb931-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fb931-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fb931-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb931-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb931-105">Används för att implementera `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="fb931-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="fb931-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fb931-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="fb931-107">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fb931-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="fb931-108">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="fb931-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="fb931-109">höger: ' t ']</span><span class="sxs-lookup"><span data-stu-id="fb931-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="fb931-110">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fb931-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fb931-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="fb931-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fb931-112">Inte</span><span class="sxs-lookup"><span data-stu-id="fb931-112">'T</span></span>

