---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEC
title: ApplyLEOperationOnPhaseLEC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEC
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 60d84e2f6c3693ba0c40e2eb034b658ac8097ad8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843764"
---
# <a name="applyleoperationonphaselec-operation"></a>ApplyLEOperationOnPhaseLEC-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd som tar ett <xref:microsoft.quantum.arithmetic.phaselittleendian> register som inloggat på ett mål register av typen <xref:microsoft.quantum.arithmetic.littleendian> .

```qsharp
operation ApplyLEOperationOnPhaseLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Ctl
```


## <a name="input"></a>Indata

### <a name="op--littleendian--unit--is-ctl"></a>OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL

Åtgärden som ska tillämpas.


### <a name="target--phaselittleendian"></a>mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Registret som åtgärden tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Registret omvandlas till `LittleEndian` genom att använda <xref:microsoft.quantum.canon.qftle> och returneras sedan till dess ursprungliga representation efter tillämpning av `op` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)