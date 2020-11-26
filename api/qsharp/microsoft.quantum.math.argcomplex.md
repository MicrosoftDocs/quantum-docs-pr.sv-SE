---
uid: Microsoft.Quantum.Math.ArgComplex
title: Funktionen ArgComplex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211108"
---
# <a name="argcomplex-function"></a><span data-ttu-id="11e4d-102">Funktionen ArgComplex</span><span class="sxs-lookup"><span data-stu-id="11e4d-102">ArgComplex function</span></span>

<span data-ttu-id="11e4d-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="11e4d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="11e4d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11e4d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11e4d-105">Returnerar fasen för ett komplext tal av typen `Complex` .</span><span class="sxs-lookup"><span data-stu-id="11e4d-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="11e4d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="11e4d-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="11e4d-107">inmatade: [komplexa](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="11e4d-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="11e4d-108">Komplext tal $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="11e4d-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="11e4d-109">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="11e4d-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="11e4d-110">Fas $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="11e4d-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>