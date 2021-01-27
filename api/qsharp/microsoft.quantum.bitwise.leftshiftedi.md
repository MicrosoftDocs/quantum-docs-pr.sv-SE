---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Funktionen LeftShiftedI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845311"
---
# <a name="leftshiftedi-function"></a>Funktionen LeftShiftedI

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```