---
uid: Microsoft.Quantum.Core.RangeReverse
title: Funktionen RangeReverse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727441"
---
# <a name="rangereverse-function"></a>Funktionen RangeReverse

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paketfilerna [](https://nuget.org/packages/)


Returnerar ett nytt intervall som är omvänt från det angivna intervallet.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Indata

### <a name="r--range"></a>r: [intervall](xref:microsoft.quantum.lang-ref.range)

Indataområde.



## <a name="output--range"></a>Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)

Ett nytt intervall som är omvänt i det aktuella intervallet.

## <a name="remarks"></a>Kommentarer

Observera att omvänt i ett intervall inte bara är `end` det enda... `-step` `start` , eftersom det sista elementet i ett intervall inte kan vara detsamma som `end` .