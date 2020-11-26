---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: b749013584c89273375da002ac36b3575085b7f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219302"
---
# <a name="applyand-operation"></a>ApplyAnd-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverterar en specifik mål-qubit, om och bara om båda kontroll qubits är i läget 1, med hjälp av mått för att utföra den angränsande åtgärden.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Inverterar `target` om och endast om båda kontrollerna är 1, men antar att de `target` är i tillstånd 0.  Åtgärden har T-Count 4, T-djup 2 och kräver ingen hjälp-qubit och kan därför vara bättre för en CCNOT-åtgärd, om `target` är känt som 0.  Det angränsande av den här åtgärden är mått baserat och kräver inga T-grindar.

Det kontrollerade programmet för den här åtgärden kräver ingen hjälps qubit, `2^c` `Rz` portar och är inte optimerat för djup, där `c` är antalet övergripande kontroll qubits, inklusive de två kontrollerna från `ApplyAnd` åtgärden.  Det intilliggande kontrollerade programmet kräver `2^c - 1` `Rz` portar (med en vinkel som är två gånger så stor som den icke-angränsande), ingen hjälps qubit och inte är optimerad för djupet.

## <a name="input"></a>Indata

### <a name="control1--qubit"></a>control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Första kontrollen qubit


### <a name="control2--qubit"></a>control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit för andra kontrollen


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Mål tilläggs qubit; måste vara i tillstånd 0



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

- Cody Jones: "nya byggen för den feltoleranta Toffoli-porten", inventering. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328
- Craig Gidney: "hälften av kostnaden för Quantum addition", Quantum 2, sida 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) Doi: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "Quantum Oracle-kretsar och jul träds mönstret", [blogg artikel från 19 December 2019](https://msoeken.github.io/blog_qac.html) (Obs! förklarar den flera styrda konstruktionen)