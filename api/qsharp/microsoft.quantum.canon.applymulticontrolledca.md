---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841680"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en multiplicerad, kontrollerad version av en åtgärd med enkel kontroll.
Modifieraren `CA` anger att en enskild-qubit-åtgärd är kontrollerbar och adjointable.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

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

- [*Michael A. Nielsen, Isak L. Chuang*, Quantum-beräkning och Quantum-information](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)