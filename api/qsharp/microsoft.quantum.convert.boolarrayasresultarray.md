---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: Funktionen BoolArrayAsResultArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834195"
---
# <a name="boolarrayasresultarray-function"></a>Funktionen BoolArrayAsResultArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar en `Bool[]` typ till en `Result[]` typ, där `true` mappas till `One` och `false` mappas till `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Indata

### <a name="input--bool"></a>Indatatyp: [bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` som ska konverteras.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltigt <Result>__[]

En `Result[]` som representerar `input` .