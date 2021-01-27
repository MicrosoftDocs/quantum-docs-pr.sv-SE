---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: Funktionen ApproximateInputEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856164"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="02104-102">Funktionen ApproximateInputEncoder</span><span class="sxs-lookup"><span data-stu-id="02104-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="02104-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="02104-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="02104-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="02104-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="02104-105">Med hänsyn till en uppsättning koefficienter och en tolerans, returnerar en tillstånds förberedelse åtgärd som förbereder varje koefficient som motsvarande amplitud i ett beräknings bas tillstånd, upp till den angivna toleransen.</span><span class="sxs-lookup"><span data-stu-id="02104-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="02104-106">Indata</span><span class="sxs-lookup"><span data-stu-id="02104-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="02104-107">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="02104-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="02104-108">Den ungefärliga tolerans som ska användas för att koda de angivna koefficienterna till ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="02104-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="02104-109">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="02104-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="02104-110">De koefficienter som ska kodas till ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="02104-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="02104-111">Utdata: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="02104-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="02104-112">En tillstånds förberedelse åtgärd som förbereder angivna koefficienter som ingångs tillstånd för en specifik registrering.</span><span class="sxs-lookup"><span data-stu-id="02104-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>