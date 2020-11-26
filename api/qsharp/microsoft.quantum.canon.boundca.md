---
uid: Microsoft.Quantum.Canon.BoundCA
title: Funktionen BoundCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216890"
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

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)