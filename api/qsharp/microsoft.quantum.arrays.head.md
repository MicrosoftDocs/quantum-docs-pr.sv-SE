---
uid: Microsoft.Quantum.Arrays.Head
title: Huvud funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221121"
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