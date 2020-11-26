---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: Funktionen InputEncoder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211754"
---
# <a name="inputencoder-function"></a><span data-ttu-id="74039-102">Funktionen InputEncoder</span><span class="sxs-lookup"><span data-stu-id="74039-102">InputEncoder function</span></span>

<span data-ttu-id="74039-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="74039-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="74039-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="74039-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="74039-105">Med hänsyn till en uppsättning koefficienter och en tolerans, returnerar en tillstånds förberedelse åtgärd som förbereder varje koefficient som motsvarande amplitud i ett beräknings grund tillstånd.</span><span class="sxs-lookup"><span data-stu-id="74039-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="74039-106">Indata</span><span class="sxs-lookup"><span data-stu-id="74039-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="74039-107">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="74039-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="74039-108">De koefficienter som ska kodas till ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="74039-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="74039-109">Utdata: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="74039-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="74039-110">En tillstånds förberedelse åtgärd som förbereder angivna koefficienter som ingångs tillstånd för en specifik registrering.</span><span class="sxs-lookup"><span data-stu-id="74039-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>