---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: Funktionen BoolAsResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214253"
---
# <a name="boolasresult-function"></a>Funktionen BoolAsResult

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar en `Bool` typ till en `Result` typ, där `true` mappas till `One` och `false` mappas till `Zero` .

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>Indata

### <a name="input--bool"></a>Indatatyp: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` som ska konverteras.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

En `Result` som representerar `input` .