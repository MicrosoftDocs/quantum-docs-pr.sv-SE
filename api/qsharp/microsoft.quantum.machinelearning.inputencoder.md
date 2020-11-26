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
# <a name="inputencoder-function"></a>Funktionen InputEncoder

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med hänsyn till en uppsättning koefficienter och en tolerans, returnerar en tillstånds förberedelse åtgärd som förbereder varje koefficient som motsvarande amplitud i ett beräknings grund tillstånd.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Indata

### <a name="coefficients--double"></a>koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

De koefficienter som ska kodas till ingångs tillstånd.



## <a name="output--stategenerator"></a>Utdata: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

En tillstånds förberedelse åtgärd som förbereder angivna koefficienter som ingångs tillstånd för en specifik registrering.