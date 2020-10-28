---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: Funktionen BoolAsResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727594"
---
# <a name="boolasresult-function"></a>Funktionen BoolAsResult

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paketfilerna [](https://nuget.org/packages/)


Konverterar en `Bool` typ till en `Result` typ, där `true` mappas till `One` och `false` mappas till `Zero` .

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>Indata

### <a name="input--bool"></a>Indatatyp: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` som ska konverteras.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

En `Result` som representerar `input` .