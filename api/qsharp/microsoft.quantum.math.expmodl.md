---
uid: Microsoft.Quantum.Math.ExpModL
title: Funktionen ExpModL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848359"
---
# <a name="expmodl-function"></a>Funktionen ExpModL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Description

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