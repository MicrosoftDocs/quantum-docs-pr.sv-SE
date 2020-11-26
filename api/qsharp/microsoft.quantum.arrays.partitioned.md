---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Partitionerad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220509"
---
# <a name="partitioned-function"></a>Partitionerad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Delar upp en matris i flera delar.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Indata

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)[]

Antal element i varje del av matrisen


### <a name="arr--t"></a>arr: ' t []

Inmatad matris som ska delas.



## <a name="output--t"></a>Utdata: ' t [] []

Flera matriser där den första matrisen är den första `nElements[0]` av `arr` och den andra matrisen är nästa `nElements[1]` i `arr` osv. Den sista matrisen kommer att innehålla alla återstående element.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

