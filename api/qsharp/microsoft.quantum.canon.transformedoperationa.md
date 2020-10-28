---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: Funktionen TransformedOperationA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 349424a102dba7354bbaa65fffdc2b5d506a3b91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728341"
---
# <a name="transformedoperationa-function"></a>Funktionen TransformedOperationA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Med en funktion och en åtgärd returnerar en ny åtgärd vars Indatatyp omvandlas av den angivna funktionen.

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="fn--u---t"></a>FN: U->

En funktion som transformerar den angivna ingången i ett formulär som förväntas av åtgärden.


### <a name="op--t--unit-adj"></a>OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

Åtgärden som ska transformeras.



## <a name="output--u--unit-adj"></a>Utdata: ' U => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

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