---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Funktionen LeftShiftedI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729878"
---
# <a name="leftshiftedi-function"></a>Funktionen LeftShiftedI

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paketfilerna [](https://nuget.org/packages/)


Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Indata

### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).


### <a name="amount--int"></a>belopp: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar som ska `value` flyttas till vänster.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Värdet för `value` , flyttas till vänster med `amount` bitar.

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```