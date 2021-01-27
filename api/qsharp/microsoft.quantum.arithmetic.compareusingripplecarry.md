---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843293"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Den här åtgärden testar om ett heltal som representeras av ett register över qubits är större än ett annat heltal, och använder en XOR av resultatet på en qubit.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

`x` `y` Den här åtgärden kontrollerar om det finns två heltal och lagras i qubit-register med samma storlek `x > y` . Om värdet är True är 1 XORed till en qubit för utdata. Annars är 0 XORed till en qubit för utdata.
Med andra ord kan den här åtgärden representeras av den enhetliga $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.
\end{align} $ $

## <a name="input"></a>Indata

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Det första talet som ska jämföras lagrade i `LittleEndian` format i ett qubit-register.


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Det andra talet som ska jämföras lagrade i `LittleEndian` ett qubit-register.


### <a name="output--qubit"></a>utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som lagrar resultatet av jämförelsen $x>y $.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

- En ny Quantum krusning-tillsatsering-krets Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184