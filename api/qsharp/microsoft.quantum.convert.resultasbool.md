---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: Funktionen ResultAsBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832552"
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