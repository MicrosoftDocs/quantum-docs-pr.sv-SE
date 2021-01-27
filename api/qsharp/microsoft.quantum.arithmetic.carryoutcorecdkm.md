---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843333"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kärn åtgärden i RippleCarryAdderCDKM, som används med ovanstående ApplyOuterCDKMAdder-åtgärd, som har avvisats med den här åtgärden för att hämta den inre driften av RippleCarryAdderCDKM. Den här åtgärden beräknar qubit och tillämpar en sekvens av inte portar på en del av indatan `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Första qubit-registrering.


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Andra qubit-registrering.


### <a name="ancilla--qubit"></a>Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ancilla-qubit som används i RippleCarryAdderCDKM har skickats till den här åtgärden.


### <a name="carry--qubit"></a>bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Utför qubit i RippleCarryAdderCDKM-åtgärden.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

- Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum krusning-Drive-extra kretsen", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1