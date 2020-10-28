---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730955"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


Vid en lyckad sannolikhet returnerar en enskild Bernoulli-utvärdering som är sann med den aktuella sannolikheten.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Indata

### <a name="successprobability--double"></a>successProbability: [dubbel](xref:microsoft.quantum.lang-ref.double)

Sannolikheten som `true` ska returneras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` med sannolikhet `successProbability` och `false` sannolikhet `1.0 - successProbability` .