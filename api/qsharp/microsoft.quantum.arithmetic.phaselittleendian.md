---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842989"
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