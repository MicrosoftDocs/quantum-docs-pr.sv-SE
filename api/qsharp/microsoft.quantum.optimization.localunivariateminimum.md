---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Funktionen LocalUnivariateMinimum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726493"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="ed54c-102">Funktionen LocalUnivariateMinimum</span><span class="sxs-lookup"><span data-stu-id="ed54c-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="ed54c-103">Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="ed54c-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="ed54c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed54c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed54c-105">Returnerar det lokala minimivärdet för en univariate-funktion under ett begränsat intervall med hjälp av en gyllene intervalls ökning.</span><span class="sxs-lookup"><span data-stu-id="ed54c-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="ed54c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ed54c-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="ed54c-107">FN: [dubbel](xref:microsoft.quantum.lang-ref.double) -> [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed54c-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed54c-108">Univariate-funktionen som ska minimeras.</span><span class="sxs-lookup"><span data-stu-id="ed54c-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="ed54c-109">gränser: ([dubbel](xref:microsoft.quantum.lang-ref.double),[dubbel](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="ed54c-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="ed54c-110">Intervallet som det lokala minimivärdet ska hittas i.</span><span class="sxs-lookup"><span data-stu-id="ed54c-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ed54c-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed54c-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed54c-112">Noggrannheten i funktionen indatatyper som ska tolereras.</span><span class="sxs-lookup"><span data-stu-id="ed54c-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="ed54c-113">Sökningen efter lokal OPTIMA fortsätter tills intervallet är mindre än denna tolerans.</span><span class="sxs-lookup"><span data-stu-id="ed54c-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="ed54c-114">Utdata: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="ed54c-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="ed54c-115">En lokal OPTIMA för den aktuella funktionen, som finns inom de tilldelade gränserna.</span><span class="sxs-lookup"><span data-stu-id="ed54c-115">A local optima of the given function, located within the given bounds.</span></span>