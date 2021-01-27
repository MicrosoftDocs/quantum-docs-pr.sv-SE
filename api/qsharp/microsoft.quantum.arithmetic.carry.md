---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Utföra åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843357"
---
# <a name="carry-operation"></a>Utföra åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementerar en omvänd bär grind. En driven bit som är kodad i qubit `carryIn` och två summand-bitar som är kodad i `summand1` och `summand2` , beräknar den bitvisa XOR `carryIn` `summand1` och `summand2` i qubit `summand2` och XoReD till qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="carryin--qubit"></a>transportera: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Första summand-qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Andra summand-qubit ersätts med den nedre biten av summan av `summand1` och `summand2` .


### <a name="carryout--qubit"></a>över: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, kommer att XoReD med den högre bit summan.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

