---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222430"
---
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian-användardefinierad typ

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Små endian-osignerade heltal i QFT-basen.

Om t. ex. $ \ket{x} $ är den lilla endian-kodningen av heltals-$x $ i beräknings basen, är $ \operatorname{QFTLE} \ket{x} $ kodningen för $x $ i QFT-basen.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Kommentarer

Vi förkortar `PhaseLittleEndian` som `PhaseLE` i dokumentationen.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)