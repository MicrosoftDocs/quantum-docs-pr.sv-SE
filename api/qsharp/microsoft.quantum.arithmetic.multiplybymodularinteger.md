---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222583"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför modulär multiplikation med en heltalskonstant i ett qubit-register.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Låt oss ange `modulus` $N $ och `constMultiplier` $a $.
Den här åtgärden implementerar sedan en enhetlig åtgärd som definieras av följande karta i beräknings basen: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ för alla $y $ mellan $0 $ och $N-$1.

## <a name="input"></a>Indata

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Konstant enligt vilken multiplikatorn multipliceras. Måste vara co-primtal till Modulus.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Multiplikations åtgärden utförs med modulo `modulus` .


### <a name="multiplier--littleendian"></a>multiplikator: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Talet multipliceras med en konstant.
Detta är en matris med qubits som kodar ett heltal i format med liten endian.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

- För krets diagrammet och förklaring, se figur 7 på [sidan 8 av arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Den här åtgärden motsvarar U ₐ i [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)