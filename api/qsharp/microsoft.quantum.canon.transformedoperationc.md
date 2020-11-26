---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: Funktionen TransformedOperationC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 964576788bc80dd8920acdfb62d5d69a060e75f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204869"
---
# <a name="transformedoperationc-function"></a>Funktionen TransformedOperationC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="fn--u---t"></a>FN: U->

En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.


### <a name="op--t--unit--is-ctl"></a>OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL

Åtgärden som ska transformeras.



## <a name="output--u--unit--is-ctl"></a>Utdata: U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd tbat anropar `fn` sina indata och skickar sedan resultatet till `op` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="u"></a>' U



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. sammansatt](xref:Microsoft.Quantum.Canon.Composed)