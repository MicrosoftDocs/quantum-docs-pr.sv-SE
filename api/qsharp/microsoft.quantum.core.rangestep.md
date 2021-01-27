---
uid: Microsoft.Quantum.Core.RangeStep
title: Funktionen RangeStep
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853605"
---
# <a name="rangestep-function"></a>Funktionen RangeStep

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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