---
uid: Microsoft.Quantum.Arrays.Merged
title: Sammanfogad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845616"
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

