---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729619"
---
# <a name="applyfermionicswap-operation"></a>ApplyFermionicSWAP-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Tillämpar Fermionic-VÄXLINGen.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a>Beskrivning

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

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, Jonas McClain, Hartmut Neven, Garnet Kin-Lic-kanal* , arXiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. inbyggd. växling](xref:Microsoft.Quantum.Intrinsic.SWAP)