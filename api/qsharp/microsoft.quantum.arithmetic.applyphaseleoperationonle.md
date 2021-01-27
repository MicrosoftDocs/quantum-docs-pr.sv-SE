---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: d94fdb55e051e76dd518eff14b80d1a24516bf8a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843682"
---
# <a name="applyphaseleoperationonle-operation"></a>ApplyPhaseLEOperationOnLE-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd som tar ett <xref:microsoft.quantum.arithmetic.littleendian> register som inloggat på ett mål register av typen <xref:microsoft.quantum.arithmetic.phaselittleendian> .

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Indata

### <a name="op--phaselittleendian--unit"></a>OP: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden som ska tillämpas.


### <a name="target--littleendian"></a>mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registret som åtgärden tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Registret omvandlas till `PhaseLittleEndian` genom att använda <xref:microsoft.quantum.canon.qftle> och returneras sedan till dess ursprungliga representation efter tillämpning av `op` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLECA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)