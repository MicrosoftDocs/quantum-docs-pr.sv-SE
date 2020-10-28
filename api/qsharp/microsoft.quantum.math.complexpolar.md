---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725905"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar-användardefinierad typ

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Representerar ett komplext tal i polär form.

Den polära representationen av ett komplext tal är $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="magnitude--double"></a>Storlek: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det absoluta värdet $r \ge $0 av $c $.
### <a name="argument--double"></a>Argument: [Double](xref:microsoft.quantum.lang-ref.double)

Fasen $t \in \mathbb R $ av $c $.