---
uid: Microsoft.Quantum.Canon.BoundA
title: Bindnings funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216956"
---
# <a name="bounda-function"></a>Bindnings funktion

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.
Modifieraren `A` anger att alla åtgärder i matrisen är adjointable.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="operations--t--unit--is-adj"></a>åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just []

En sekvens med åtgärder som ska utföras på en specifik Indatatyp.



## <a name="output--t--unit--is-adj"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som varje åtgärd i matrisen agerar på.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)