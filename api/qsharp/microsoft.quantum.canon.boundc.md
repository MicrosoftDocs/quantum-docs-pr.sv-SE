---
uid: Microsoft.Quantum.Canon.BoundC
title: Funktionen BoundC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841036"
---
# <a name="boundc-function"></a>Funktionen BoundC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.
Modifieraren `C` anger att alla åtgärder i matrisen är kontrollerbara.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="operations--t--unit--is-ctl"></a>åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL []

En sekvens med åtgärder som ska utföras på en specifik Indatatyp.



## <a name="output--t--unit--is-ctl"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som varje åtgärd i matrisen agerar på.

## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

och

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)