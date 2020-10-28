---
uid: Microsoft.Quantum.Core.RangeStart
title: Rang funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727414"
---
# <a name="rangestart-function"></a>Rang funktion

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paketfilerna [](https://nuget.org/packages/)


Returnerar det definierade startvärdet för det angivna intervallet.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Indata

### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Det definierade startvärdet för det angivna intervallet.

## <a name="remarks"></a>Kommentarer

Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.

Observera att det definierade startvärdet för ett intervall är detsamma som det första elementet i sekvensen, om inte intervallet anger en tom sekvens (till exempel 2.. 1).