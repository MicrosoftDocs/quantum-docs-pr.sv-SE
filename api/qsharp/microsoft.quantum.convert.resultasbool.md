---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: Funktionen ResultAsBool
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: a170acf635e4e2b2150ffc208fabc9782ff837b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224181"
---
# <a name="resultasbool-function"></a>Funktionen ResultAsBool

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar en `Result` typ till en `Bool` typ, där `One` mappas till `true` och `Zero` mappas till `false` .

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a>Indata

### <a name="input--__invalidresult__"></a>inmatade: __ogiltig <Result>__

`Result` som ska konverteras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

En `Bool` som representerar `input` .