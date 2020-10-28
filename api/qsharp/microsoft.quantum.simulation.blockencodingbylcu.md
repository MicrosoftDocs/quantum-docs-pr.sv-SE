---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: Funktionen BlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733710"
---
# <a name="blockencodingbylcu-function"></a>Funktionen BlockEncodingByLCU

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Kodar en operatör av intresse till en `BlockEncoding` .

Detta skapar en `BlockEncoding` enhetlig $U = P\cdot V\cdot P ^ \dagger $ som kodar vissa operatorer $H = \ sum_ {j} | \ alpha_j | U_j $ intresse som är en linjär kombination av unitaries. $P $ är vanligt vis en enhetlig tillstånds förberedelse som $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ och $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En enhetlig $P $ som förbereder ett visst mål tillstånd.


### <a name="selector--ts--unit-adj--ctl"></a>väljare: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En enhetlig $V $ som kodar komponenten unitaries i $H $.



## <a name="output--ts--unit-adj--ctl"></a>Utdata: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En enhetlig $U $ som agerar gemensamt på registren `a` och `s` som blockerar-kodar $H $ och uppfyller $U ^ \Dagger = U $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="s"></a>Formulär



## <a name="remarks"></a>Kommentarer

Den här `BlockEncoding` implementeringen ger den egenskaperna för en `BlockEncodingReflection` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulering. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)