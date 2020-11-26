---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Kvadratiski-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221869"
---
# <a name="squarei-operation"></a>Kvadratiski-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Beräknar kvadraten av heltalet `xs` i `result` , som måste vara noll först.

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit Number till Square (LittleEndian)


### <a name="result--littleendian"></a>resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$2N $-bit result (LittleEndian) måste ha statusen $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Använder en vanlig Shift-och-Lägg-metod för att beräkna fyr kanten. Sparar $n-$1-qubits jämfört med den enkla lösningen som först kopierar x x innan en vanlig multiplikator appliceras och sedan ångrar kopierings åtgärden.