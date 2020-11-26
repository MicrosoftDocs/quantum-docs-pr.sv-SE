---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Funktionen RightShiftedI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209782"
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

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```