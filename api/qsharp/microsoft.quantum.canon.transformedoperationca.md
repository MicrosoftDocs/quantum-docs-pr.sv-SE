---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: Funktionen TransformedOperationCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: bb39530ae28e17d07a6a5c2bb2d35f81be312d15
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840129"
---
# <a name="transformedoperationca-function"></a>Funktionen TransformedOperationCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="fn--u---t"></a>FN: U->

En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.


### <a name="op--t--unit--is-adj--ctl"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Åtgärden som ska transformeras.



## <a name="output--u--unit--is-adj--ctl"></a>Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="u"></a>' U



## <a name="example"></a>Exempel

Följande anrop använder @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" för att transformera en åtgärd som har utformats för @"Microsoft.Quantum.Arithmetic.BigEndian" indata till en åtgärd som accepterar indata av typen @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. sammansatt](xref:Microsoft.Quantum.Canon.Composed)