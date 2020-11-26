---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 2d5703eed3a3b6e611ae7c993febf018fcb148b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218418"
---
# <a name="applymulticontrolledc-operation"></a>ApplyMultiControlledC-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en multiplicerad, kontrollerad version av en åtgärd med enkel kontroll.
Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Indata

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd som styrs av en enskild qubit.
Den första qubit i argumentet för åtgärden antas vara en kontroll och resten antas vara mål qubits.
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

- [Microsoft. Quantum. Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)