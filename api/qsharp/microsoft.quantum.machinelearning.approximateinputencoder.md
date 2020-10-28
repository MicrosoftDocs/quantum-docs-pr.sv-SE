---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: Funktionen ApproximateInputEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731126"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="a439b-102">Funktionen ApproximateInputEncoder</span><span class="sxs-lookup"><span data-stu-id="a439b-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="a439b-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a439b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a439b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a439b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a439b-105">Med hänsyn till en uppsättning koefficienter och en tolerans, returnerar en tillstånds förberedelse åtgärd som förbereder varje koefficient som motsvarande amplitud i ett beräknings bas tillstånd, upp till den angivna toleransen.</span><span class="sxs-lookup"><span data-stu-id="a439b-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="a439b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a439b-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a439b-107">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a439b-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a439b-108">Den ungefärliga tolerans som ska användas för att koda de angivna koefficienterna till ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a439b-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="a439b-109">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a439b-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a439b-110">De koefficienter som ska kodas till ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a439b-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="a439b-111">Utdata: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="a439b-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="a439b-112">En tillstånds förberedelse åtgärd som förbereder angivna koefficienter som ingångs tillstånd för en specifik registrering.</span><span class="sxs-lookup"><span data-stu-id="a439b-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>