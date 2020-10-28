---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729469"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Använder en multiplicerad, kontrollerad version av en åtgärd med enkel kontroll.
Modifieraren `CA` anger att en enskild-qubit-åtgärd är kontrollerbar och adjointable.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="singlycontrolledop--qubit--unit-adj"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

En åtgärd som styrs av en enskild qubit.
Den första qubit i argumentet för åtgärden förutsätter vara en kontroll och resten antas vara mål qubits.
`ApplyMultiControlled` anropar alltid `singlyControlledOp` med ett argument av längden minst 1.


### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Den kontrollerade-styrda-inte porten som ska användas för konstruktion.


### <a name="controls--qubit"></a>kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Den qubits som ska `singlyControlledOp` kontrol leras på.
Längden `controls` måste vara minst 1.


### <a name="targets--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Den mål-qubits som `singlyControlledOp` reagerar på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den här åtgärden använder bara ren Ancilla-qubits.

För förklaringen och krets diagrammet se bild 4,10, avsnitt 4,3 i Nielsen & Chuang

## <a name="references"></a>Referenser

- [*Michael A. Nielsen, Isak L. Chuang* , Quantum-beräkning och Quantum-information](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)