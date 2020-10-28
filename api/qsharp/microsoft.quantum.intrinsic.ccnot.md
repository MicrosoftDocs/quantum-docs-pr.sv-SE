---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726715"
---
# <a name="ccnot-operation"></a>CCNOT-åtgärd

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paketfilerna [](https://nuget.org/packages/)


Använder den dubbla styrda, inte (CCNOT) porten till tre qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="control1--qubit"></a>control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Första kontrollen qubit för CCNOT-porten.


### <a name="control2--qubit"></a>control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Den andra kontrollen qubit för CCNOT-porten.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Mål-qubit för CCNOT-porten.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Motsvarar:

```qsharp
Controlled X([control1, control2], target);
```