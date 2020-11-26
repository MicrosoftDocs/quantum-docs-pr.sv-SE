---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192969"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vid en lyckad sannolikhet returnerar en enskild Bernoulli-utvärdering som är sann med den aktuella sannolikheten.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Indata

### <a name="successprobability--double"></a>successProbability: [dubbel](xref:microsoft.quantum.lang-ref.double)

Sannolikheten som `true` ska returneras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` med sannolikhet `successProbability` och `false` sannolikhet `1.0 - successProbability` .