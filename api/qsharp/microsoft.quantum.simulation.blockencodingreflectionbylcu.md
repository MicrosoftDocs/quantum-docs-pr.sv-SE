---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: Funktionen BlockEncodingReflectionByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733171"
---
# <a name="blockencodingreflectionbylcu-function"></a>Funktionen BlockEncodingReflectionByLCU

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Kodar en operatör av intresse till en `BlockEncodingReflection` .

Detta skapar en `BlockEncodingReflection` enhetlig $U = P\cdot V\cdot P ^ \dagger $ som kodar vissa operatorer $H = \ sum_ {j} | \ alpha_j | U_j $ intresse som är en linjär kombination av unitaries. $P $ är vanligt vis en enhetlig tillstånds förberedelse som $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ och $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Indata

### <a name="statepreparation--qubit--unit-adj--ctl"></a>statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL

En enhetlig $P $ som förbereder ett visst mål tillstånd.


### <a name="selector--qubitqubit--unit-adj--ctl"></a>väljare: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL

En enhetlig $V $ som kodar komponenten unitaries i $H $.



## <a name="output--blockencodingreflection"></a>Utdata: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

En enhetlig $U $ som agerar gemensamt på registren `a` och `s` som blockerar-kodar $H $ och uppfyller $U ^ {-1} = U $.

## <a name="remarks"></a>Kommentarer

Den här `BlockEncoding` implementeringen ger den egenskaperna för en `BlockEncodingReflection` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulering. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)