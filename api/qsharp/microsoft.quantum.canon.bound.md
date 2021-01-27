---
uid: Microsoft.Quantum.Canon.Bound
title: Bound-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841053"
---
# <a name="bound-function"></a>Bound-funktion

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris med åtgärder som agerar på samma indatamängd skapar en ny åtgärd som utför varje åtgärd i följd.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Indata

### <a name="operations--t--unit-"></a>åtgärder: ' t => [enhet](xref:microsoft.quantum.lang-ref.unit) []

En sekvens med åtgärder som ska utföras på en specifik Indatatyp.



## <a name="output--t--unit"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd som utför varje åtgärd i följd av dess inaktuella Indatatyp.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som varje åtgärd i matrisen agerar på.

## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
let bound = Bound([U, V]);
bound(x);
```

och

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Quantum. Canon. Boundas](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. Quantum. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)