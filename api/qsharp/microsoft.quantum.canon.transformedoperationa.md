---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: Funktionen TransformedOperationA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: eceba260e601b73bdfa2de6ea6ab146820b5c59a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204886"
---
# <a name="transformedoperationa-function"></a>Funktionen TransformedOperationA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="fn--u---t"></a>FN: U->

En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.


### <a name="op--t--unit--is-adj"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

Åtgärden som ska transformeras.



## <a name="output--u--unit--is-adj"></a>Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="u"></a>' U



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. sammansatt](xref:Microsoft.Quantum.Canon.Composed)