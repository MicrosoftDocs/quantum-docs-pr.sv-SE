---
uid: Microsoft.Quantum.Math.PlusA
title: Plus-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842702"
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