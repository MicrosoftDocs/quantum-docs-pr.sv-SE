---
uid: Microsoft.Quantum.Canon.CY
title: CY-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728782"
---
# <a name="cy-operation"></a>CY-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Tillämpar den kontrollerade Y-porten (CY) på ett par med qubits.

$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 &-i \\ \\ 0 & 0 & i & 0 \end{align} $ $ där rader och kolumner är ordnade som i Quantum Concepts-guiden.

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="control--qubit"></a>kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Styr qubit för CY-grinden.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Mål-qubit för CY-grinden.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Motsvarar:

```qsharp
Controlled Y([control], target);
```