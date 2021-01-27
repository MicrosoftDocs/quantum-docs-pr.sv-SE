---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854494"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en reflektions-Oracle.

En reflektions-Oracle, $O $, har indata:

- Den fas $ \phi $ som det reflekterande del utrymmet ska roteras med.
- Qubit-registret som den aktuella reflektionen ska utföras på.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Namngivna objekt

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL



## <a name="remarks"></a>Kommentarer

Den här Oracle $O = \boldone – (1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ utför en delvis reflektion av en fas $ \phi $ om ett enda rent tillstånd $ \ket{\psi} $.