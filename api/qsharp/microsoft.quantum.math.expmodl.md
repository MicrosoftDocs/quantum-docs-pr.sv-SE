---
uid: Microsoft.Quantum.Math.ExpModL
title: Funktionen ExpModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210761"
---
# <a name="expmodl-function"></a>Funktionen ExpModL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Beskrivning

Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.
Funktionen returnerar $x ^ p \operatorname{mod} N $.

Vi förutsätter att $N $, $x $ är positiva och är inte negativt.

## <a name="input"></a>Indata

### <a name="expbase--bigint"></a>expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>effekt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Kommentarer

Tar tid i proportion till antalet bitar i `power` , inte `power` själva.