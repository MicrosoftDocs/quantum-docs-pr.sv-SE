---
uid: Microsoft.Quantum.Arrays.Merged
title: Sammanfogad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220645"
---
# <a name="merged-function"></a>Sammanfogad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med två sorterade matriser returnerar en enskild matris som innehåller elementen i både i sorterad ordning. Används internt genom sammanslagnings sortering.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="comparison--tt---bool"></a>jämförelse: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>vänster: ' ' []




### <a name="right--t"></a>höger: ' t ']





## <a name="output--t"></a>Utdata: ' t []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

