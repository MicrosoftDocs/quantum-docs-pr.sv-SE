---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850440"
---
# <a name="applytotail-operation"></a>ApplyToTail-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på det sista elementet i en matris.

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

En specifik åtgärd `op` och en matris med mål `targets` gäller `op(Tail(targets))` .

## <a name="input"></a>Indata

### <a name="op--t--unit"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd som ska tillämpas.


### <a name="targets--t"></a>mål: ' t []

En matris med mål som den sista kommer att tillämpas på `op` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas.

## <a name="example"></a>Exempel

Följande Q #-kodfragment är likvärdiga:

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToTailA](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. Quantum. Canon. ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. Quantum. Canon. ApplyToTailCA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)