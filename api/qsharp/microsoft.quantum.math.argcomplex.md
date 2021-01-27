---
uid: Microsoft.Quantum.Math.ArgComplex
title: Funktionen ArgComplex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842762"
---
# <a name="argcomplex-function"></a><span data-ttu-id="97774-102">Funktionen ArgComplex</span><span class="sxs-lookup"><span data-stu-id="97774-102">ArgComplex function</span></span>

<span data-ttu-id="97774-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="97774-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="97774-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97774-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97774-105">Returnerar fasen för ett komplext tal av typen `Complex` .</span><span class="sxs-lookup"><span data-stu-id="97774-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="97774-106">Indata</span><span class="sxs-lookup"><span data-stu-id="97774-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="97774-107">inmatade: [komplexa](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="97774-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="97774-108">Komplext tal $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="97774-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="97774-109">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97774-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97774-110">Fas $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="97774-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>