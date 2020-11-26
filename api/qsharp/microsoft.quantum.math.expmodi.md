---
uid: Microsoft.Quantum.Math.ExpModI
title: Funktionen ExpModI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228499"
---
# <a name="expmodi-function"></a>Funktionen ExpModI

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Beskrivning

Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.
Funktionen returnerar $x ^ p \operatorname{mod} N $.

Vi förutsätter att $N $, $x $ är positiva och är inte negativt.

## <a name="input"></a>Indata

### <a name="expbase--int"></a>expBase: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Kommentarer

Tar tid i proportion till antalet bitar i `power` , inte `power` själva.