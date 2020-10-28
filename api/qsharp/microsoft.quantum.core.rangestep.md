---
uid: Microsoft.Quantum.Core.RangeStep
title: Funktionen RangeStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727411"
---
# <a name="rangestep-function"></a>Funktionen RangeStep

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paketfilerna [](https://nuget.org/packages/)


Returnerar det heltal som anger hur nästa värde i ett intervall beräknas.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Indata

### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Det definierade stegvärdet för det angivna intervallet.

## <a name="remarks"></a>Kommentarer

Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.