---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: Funktionen ArgComplexPolar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195774"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="f0aae-102">Funktionen ArgComplexPolar</span><span class="sxs-lookup"><span data-stu-id="f0aae-102">ArgComplexPolar function</span></span>

<span data-ttu-id="f0aae-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f0aae-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f0aae-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0aae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0aae-105">Returnerar fasen för ett komplext tal av typen `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="f0aae-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="f0aae-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f0aae-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="f0aae-107">inmatade: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f0aae-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f0aae-108">Komplext tal $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="f0aae-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="f0aae-109">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0aae-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0aae-110">Fas $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="f0aae-110">Phase $\text{Arg}[c] = t$.</span></span>