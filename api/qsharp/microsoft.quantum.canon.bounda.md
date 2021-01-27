---
uid: Microsoft.Quantum.Canon.BoundA
title: Bindnings funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844546"
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

## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

och

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)