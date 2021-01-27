---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819032"
---
# <a name="ccnot-operation"></a>CCNOT-åtgärd

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Använder den dubbla styrda, inte (CCNOT) porten till tre qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
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