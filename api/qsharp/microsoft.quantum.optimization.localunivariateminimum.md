---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Funktionen LocalUnivariateMinimum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854600"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="3dd1b-102">Funktionen LocalUnivariateMinimum</span><span class="sxs-lookup"><span data-stu-id="3dd1b-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="3dd1b-103">Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="3dd1b-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="3dd1b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3dd1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3dd1b-105">Returnerar det lokala minimivärdet för en univariate-funktion under ett begränsat intervall med hjälp av en gyllene intervalls ökning.</span><span class="sxs-lookup"><span data-stu-id="3dd1b-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="3dd1b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3dd1b-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="3dd1b-107">FN: [dubbel](xref:microsoft.quantum.lang-ref.double) -> [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3dd1b-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3dd1b-108">Univariate-funktionen som ska minimeras.</span><span class="sxs-lookup"><span data-stu-id="3dd1b-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="3dd1b-109">gränser: ([dubbel](xref:microsoft.quantum.lang-ref.double),[dubbel](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="3dd1b-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="3dd1b-110">Intervallet som det lokala minimivärdet ska hittas i.</span><span class="sxs-lookup"><span data-stu-id="3dd1b-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="3dd1b-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3dd1b-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3dd1b-112">Noggrannheten i funktionen indatatyper som ska tolereras.</span><span class="sxs-lookup"><span data-stu-id="3dd1b-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="3dd1b-113">Sökningen efter lokal OPTIMA fortsätter tills intervallet är mindre än denna tolerans.</span><span class="sxs-lookup"><span data-stu-id="3dd1b-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="3dd1b-114">Utdata: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="3dd1b-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="3dd1b-115">En lokal OPTIMA för den aktuella funktionen, som finns inom de tilldelade gränserna.</span><span class="sxs-lookup"><span data-stu-id="3dd1b-115">A local optima of the given function, located within the given bounds.</span></span>