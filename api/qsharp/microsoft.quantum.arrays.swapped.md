---
uid: Microsoft.Quantum.Arrays.Swapped
title: Utbytd funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850958"
---
# <a name="swapped-function"></a>Utbytd funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en växling av två element i en matris.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="firstindex--int"></a>firstIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index för det första element som ska växlas.


### <a name="secondindex--int"></a>secondIndex: [int](xref:microsoft.quantum.lang-ref.int)

Index för det andra element som ska växlas.


### <a name="arr--t"></a>arr: ' t []

Matris med element som ska växlas.



## <a name="output--t"></a>Utdata: ' t []

Den matris som har den tillämpade växlingen på plats.

## <a name="example"></a>Exempel

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

