---
uid: Microsoft.Quantum.Arrays.Head
title: Huvud funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848579"
---
# <a name="head-function"></a>Huvud funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar det första elementet i matrisen.

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>Indata

### <a name="array--a"></a>matris: "A []

Matris som det första elementet ska hämtas från. Matrisen måste ha en längd på minst 1.



## <a name="output--a"></a>Utdata: "A

Det första elementet i matrisen.

## <a name="type-parameters"></a>Typparametrar

### <a name="a"></a>"A

Typ av mat ris element.