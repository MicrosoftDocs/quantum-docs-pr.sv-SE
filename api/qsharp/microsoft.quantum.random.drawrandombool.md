---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853695"
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

## <a name="example"></a>Exempel

Följande exempel på Q #-kodfragment vänder sig från en prioriterad mynt:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```