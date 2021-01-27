---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841710"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverterar en specifik mål-qubit, om och bara om båda kontroll qubits är i läget 1, med T-djup 1, med hjälp av mått för att utföra den angränsande åtgärden.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Inverterar `target` om och endast om båda kontrollerna är 1, men antar att de `target` är i tillstånd 0.  Åtgärden har T-Count 4, T-djup 1 och kräver en qubit och kan därför föredras för en CCNOT-åtgärd, om `target` är känt som 0.  Det angränsande av den här åtgärden är mått baserat och kräver inga T-grindar och ingen hjälps qubit.

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
- Peter selinger: "Quantum-kretsar om T-djupgående One", inventering. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) Doi: 10.1103/PhysRevA. 87.042302