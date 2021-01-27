---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: c822933340d592061eb039af7c6e438212abc265
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843838"
---
# <a name="applyinnerttkadder-operation"></a>ApplyInnerTTKAdder-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementerar funktionen inre addition för åtgärden RippleCarryAdderTTK. Det här är den inre åtgärd som är konjugaten med den yttre åtgärden för att skapa en fullständig egenskapsangivning.

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registrera det första heltalet summand inmatat på RippleCarryAdderTTK.


### <a name="ys--littleendian"></a>gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registrera det andra heltalet summand inmatat på RippleCarryAdderTTK.


### <a name="carry--qubit"></a>bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Bär qubit, är XoReD med den mest signifikanta biten av summan.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den angivna kontrollerade åtgärden använder symmetri och ömsesidig annullering av åtgärder för att förbättra standard implementeringen som lägger till en kontroll i varje åtgärd.

## <a name="references"></a>Referenser

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition-kretsar och obegränsade fläktning", Quantum information och beräkning, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530