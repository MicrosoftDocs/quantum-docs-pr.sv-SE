---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728596"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Beräknar det logiska och flera qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits in i flera ingångar och grindar.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som utdata från och skrivs till. Detta förutsätter att alltid starta i $ \ket {0} $-tillstånd.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

När `ctrlRegister` har exakt $2 $ qubits motsvarar detta `CCNOT` åtgärden men fasen med en fas $e ^ {i \ Pi/2} $ på $ \ket {001} $ och $-e ^ {i \ Pi/2} $ på $ \ket {101} $ och $ \ket {011} $.
Det angränsande är också en metod för att mäta och korrigera som är inversen till den ursprungliga åtgärden endast i specialfall (se referenser), men använder färre T-grindar.

## <a name="references"></a>Referenser

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)