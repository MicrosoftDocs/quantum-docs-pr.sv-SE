---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: Funktionen LessThanLexographic
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815646"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="f8281-102">Funktionen LessThanLexographic</span><span class="sxs-lookup"><span data-stu-id="f8281-102">LessThanLexographic function</span></span>

<span data-ttu-id="f8281-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f8281-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f8281-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8281-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8281-105">Används för att implementera `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="f8281-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="f8281-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f8281-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="f8281-107">jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8281-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="f8281-108">vänster: ' ' []</span><span class="sxs-lookup"><span data-stu-id="f8281-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="f8281-109">höger: ' t ']</span><span class="sxs-lookup"><span data-stu-id="f8281-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="f8281-110">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8281-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f8281-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f8281-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8281-112">Inte</span><span class="sxs-lookup"><span data-stu-id="f8281-112">'T</span></span>

