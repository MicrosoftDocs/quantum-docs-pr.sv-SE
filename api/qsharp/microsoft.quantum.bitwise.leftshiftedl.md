---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Funktionen LeftShiftedL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842146"
---
# <a name="leftshiftedl-function"></a>Funktionen LeftShiftedL

Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Indata

### <a name="value--bigint"></a>värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).


### <a name="amount--int"></a>belopp: [int](xref:microsoft.quantum.lang-ref.int)

Antalet bitar som ska `value` flyttas till vänster.



## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Värdet för `value` , flyttas till vänster med `amount` bitar.

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```