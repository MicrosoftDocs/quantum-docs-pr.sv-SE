---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844767"
---
# <a name="applyquantumfouriertransform-operation"></a>ApplyQuantumFourierTransform-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i den lilla endian-representationen.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="qs--littleendian"></a>QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Quantum register till vilken Quantum Fourier-transformeringen används



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Indata och utdata antas vara i little endian kodning.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)