---
uid: Microsoft.Quantum.Canon.QFT
title: QFT-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852302"
---
# <a name="qft-operation"></a>QFT-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i big-endian-representationen.

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="qs--bigendian"></a>QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Quantum register till vilken Quantum Fourier-transformeringen används



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Indata och utdata antas vara i big endian kodning.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)