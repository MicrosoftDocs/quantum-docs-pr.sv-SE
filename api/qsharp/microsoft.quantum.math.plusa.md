---
uid: Microsoft.Quantum.Math.PlusA
title: Plus-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194839"
---
# <a name="plusa-function"></a>Plus-funktion

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar summan (sammanfogningen) av två indata.

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a>Indata

### <a name="a--element"></a>a: ' element []

Den första indatamängden $a $ som ska summeras.


### <a name="b--element"></a>b: ' element []

Den andra indatamängden $b $ som ska summeras.



## <a name="output--element"></a>Output: ' element []

Summan $a + b $.

## <a name="type-parameters"></a>Typparametrar

### <a name="element"></a>' Element

Typ av varje element i var och en av de två angivna matriserna.