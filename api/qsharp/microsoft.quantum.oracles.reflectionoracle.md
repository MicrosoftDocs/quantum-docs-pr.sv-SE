---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733339"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paketfilerna [](https://nuget.org/packages/)


Representerar en reflektions-Oracle.

En reflektions-Oracle, $O $, har indata:

- Den fas $ \phi $ som det reflekterande del utrymmet ska roteras med.
- Qubit-registret som den aktuella reflektionen ska utföras på.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Namngivna objekt

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL



## <a name="remarks"></a>Kommentarer

Den här Oracle $O = \boldone – (1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ utför en delvis reflektion av en fas $ \phi $ om ett enda rent tillstånd $ \ket{\psi} $.