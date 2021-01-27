---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: Funktionen InputEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852947"
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