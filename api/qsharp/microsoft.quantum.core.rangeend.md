---
uid: Microsoft.Quantum.Core.RangeEnd
title: Funktionen RangeEnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831372"
---
# <a name="rangeend-function"></a>Funktionen RangeEnd

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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