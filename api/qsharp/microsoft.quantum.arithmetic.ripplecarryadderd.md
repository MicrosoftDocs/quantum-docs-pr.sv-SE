---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: b87c8f25acc8854d5e8d28f58cfc99dffb92a973
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222124"
---
# <a name="ripplecarryadderd-operation"></a>RippleCarryAdderD-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reversibel, "på plats"-tillägg av två heltal.
Med två $n $-bitars heltal som är kodade i `xs` LittleEndian `ys` -registren och, och en qubit-aktivitet, beräknar åtgärden summan av de två heltalen där $n $ minst signifikanta bitar av resultatet hålls i `ys` och den sammanställda biten är XoReD till qubit `carry` .

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register encoding First Integer summand.


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register encoding det andra heltalet summand har ändrats för att innehålla $n $ minst signifikanta bitar av summan.


### <a name="carry--qubit"></a>bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Bär qubit, är XoReD med den mest signifikanta biten av summan.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den angivna kontrollerade åtgärden använder symmetri och ömsesidig annullering av åtgärder för att förbättra standard implementeringen som lägger till en kontroll i varje åtgärd.

## <a name="references"></a>Referenser

- Thomas G. Draper: "addition på en Quantum-dator", 2000.
  https://arxiv.org/abs/quant-ph/0008033