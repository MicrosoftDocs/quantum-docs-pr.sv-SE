---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Funktionen ArrangedQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841084"
---
# <a name="arrangedqubits-function"></a>Funktionen ArrangedQubits

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Arrangera kontroll, mål och hjälper qubits enligt ett index

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Description

Returnerar en qubit-matris med målet vid index 0 och kontroll i index 2 ^ i.  Hjälpens qubits infogas på alla andra positioner i matrisen.

## <a name="input"></a>Indata

### <a name="controls--qubit"></a>kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>hjälp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

