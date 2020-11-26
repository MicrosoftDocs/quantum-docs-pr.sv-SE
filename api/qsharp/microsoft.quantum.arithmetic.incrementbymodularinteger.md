---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222957"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en modulär ökning av ett qubit-register med en heltalskonstant.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Låt oss ange `increment` $a $, `modulus` genom att $N $ och Integer som är kodat i `target` $y $.
Åtgärden utför sedan följande omvandling: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} heltal kodas i litet endian-format.

## <a name="input"></a>Indata

### <a name="increment--int"></a>ökning: [int](xref:microsoft.quantum.lang-ref.int)

Heltals ökning $a $ som ska läggas till i $y $.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Integer $N $ som mods $y + a $.


### <a name="target--littleendian"></a>mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Integer $y $ i `LittleEndian` formatet som `increment` $a $ läggs till i.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Förutsätter att det initiala värdet för målet är mindre än $N $ och att ökningen $a $ är mindre än $N $.
Observera att <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementera samma åtgärd på `PhaseLittleEndian` grund av.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. aritmetiska. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)