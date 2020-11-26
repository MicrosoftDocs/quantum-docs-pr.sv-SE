---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Funktionen ArrangedQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217075"
---
# <a name="arrangedqubits-function"></a>Funktionen ArrangedQubits

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Arrangera kontroll, mål och hjälper qubits enligt ett index

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Beskrivning

Returnerar en qubit-matris med målet vid index 0 och kontroll i index 2 ^ i.  Hjälpens qubits infogas på alla andra positioner i matrisen.

## <a name="input"></a>Indata

### <a name="controls--qubit"></a>kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>hjälp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

