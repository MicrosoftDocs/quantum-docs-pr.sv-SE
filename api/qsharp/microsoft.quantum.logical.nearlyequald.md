---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: Funktionen NearlyEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814374"
---
# <a name="nearlyequald-function"></a>Funktionen NearlyEqualD

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar true om och bara om två indata är nästan identiska (det vill säga inom en tolerans på 1e-12).

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Indata

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Det första värdet som ska jämföras.


### <a name="b--double"></a>b: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och bara om `a` är nästan lika med `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```