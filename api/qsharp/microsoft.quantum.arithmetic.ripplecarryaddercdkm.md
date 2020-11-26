---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: b08d8823fd539263205aca1ee15ee69adcb163b7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222107"
---
# <a name="ripplecarryaddercdkm-operation"></a>RippleCarryAdderCDKM-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reversibel, "på plats"-tillägg av två heltal.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Med två $n $-bitars heltal som är kodade i `xs` LittleEndian `ys` -registren och, och en qubit-aktivitet, beräknar åtgärden summan av de två heltalen där $n $ minst signifikanta bitar av resultatet hålls i `ys` och den sammanställda biten är XoReD till qubit `carry` .

## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register encoding First Integer summand.


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register encoding det andra heltalet summand har ändrats för att innehålla de n minsta signifikanta bitarna av summan.


### <a name="carry--qubit"></a>bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Bär qubit, är XoReD med den mest signifikanta biten av summan.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den här åtgärden har samma funktioner som RippleCarryAdderD, men använder bara en hjälp qubit i stället för $n $.

## <a name="references"></a>Referenser

- Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum krusning-Drive-extra kretsen", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1