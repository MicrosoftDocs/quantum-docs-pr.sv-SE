---
uid: Microsoft.Quantum.Core.RangeEnd
title: Funktionen RangeEnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727447"
---
# <a name="rangeend-function"></a>Funktionen RangeEnd

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paketfilerna [](https://nuget.org/packages/)


Returnerar det definierade slutvärdet för det angivna intervallet, som inte nödvändigt vis är det sista elementet i sekvensen.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Indata

### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Det definierade slutvärdet för det angivna intervallet.

## <a name="remarks"></a>Kommentarer

Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.

Observera att det definierade slutvärdet för ett intervall kan skilja sig från det sista elementet i den sekvens som anges av intervallet; till exempel i intervallet 0... 2.. 5 det sista elementet är 4 men end-värdet är 5.