---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: Funktionen BoolAsResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0ed5c81cb80458e2f56ba2fcaac03eb92a534bea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834174"
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