---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: Funktionen NotEqualCP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 85225109a3822a9b63a231631f3d7265143418b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814407"
---
# <a name="notequalcp-function"></a><span data-ttu-id="8823d-102">Funktionen NotEqualCP</span><span class="sxs-lookup"><span data-stu-id="8823d-102">NotEqualCP function</span></span>

<span data-ttu-id="8823d-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8823d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8823d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8823d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8823d-105">Returnerar true om och endast om två indata är inte lika.</span><span class="sxs-lookup"><span data-stu-id="8823d-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="8823d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8823d-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="8823d-107">a: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="8823d-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="8823d-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="8823d-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="8823d-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="8823d-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="8823d-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="8823d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8823d-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8823d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8823d-112">`true` om och endast om `a` inte är lika med `b` .</span><span class="sxs-lookup"><span data-stu-id="8823d-112">`true` if and only if `a` is not equal to `b`.</span></span>