---
uid: Microsoft.Quantum.Math.ExpModI
title: Funktionen ExpModI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732854"
---
# <a name="expmodi-function"></a>Funktionen ExpModI

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


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