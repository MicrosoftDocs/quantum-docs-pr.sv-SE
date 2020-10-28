---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Funktionen ArrangedQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728947"
---
# <a name="arrangedqubits-function"></a>Funktionen ArrangedQubits

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


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

