---
uid: Microsoft.Quantum.Canon.BoundCA
title: Funktionen BoundCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844519"
---
# <a name="boundca-function"></a>Funktionen BoundCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.
Modifieraren `CA` anger att alla åtgärder i matrisen är adjointable och kontrollerbara.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="operations--t--unit--is-adj--ctl"></a>åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL []

En sekvens med åtgärder som ska utföras på en specifik Indatatyp.



## <a name="output--t--unit--is-adj--ctl"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som varje åtgärd i matrisen agerar på.

## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

och

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)