---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845057"
---
# <a name="applyfermionicswap-operation"></a>ApplyFermionicSWAP-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar Fermionic-VÄXLINGen.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Detta byter i princip qubits vid användning av en global fas på-1 om båda qubits är 1. Bevarar symmetrization av banor.
Mer information finns i .

Den här åtgärden representeras av den enhetliga operatorn \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 & & 1 & 0 & 0 & 0 & \\ \\ 0 \\ \\ \\ \\ -1 \\ \\ \end{bmatrix}.
\end{align}

## <a name="input"></a>Indata

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Den första qubit som ska växlas.


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Den andra qubit som ska växlas.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, Jonas McClain, Hartmut Neven, Garnet Kin-Lic-kanal*, arXiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. inbyggd. växling](xref:Microsoft.Quantum.Intrinsic.SWAP)