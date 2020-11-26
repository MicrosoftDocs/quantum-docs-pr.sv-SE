---
uid: Microsoft.Quantum.Core.RangeReverse
title: Funktionen RangeReverse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213845"
---
# <a name="rangereverse-function"></a>Funktionen RangeReverse

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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