---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Funktionen RightShiftedI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845260"
---
# <a name="rightshiftedi-function"></a>Funktionen RightShiftedI

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Indata

### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).


### <a name="amount--int"></a>belopp: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar som ska `value` flyttas till höger.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Värdet för `value` , flyttas direkt med `amount` bitar.

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```