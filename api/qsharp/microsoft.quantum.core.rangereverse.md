---
uid: Microsoft.Quantum.Core.RangeReverse
title: Funktionen RangeReverse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853648"
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