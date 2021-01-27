---
uid: Microsoft.Quantum.Canon.Angle
title: Funktionen vinkel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842041"
---
# <a name="angle-function"></a>Funktionen vinkel

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar 1, om `index` har ett udda antal 1s och-1, om `index` har ett jämnt antal 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Description

Värdet motsvarar tecknet för koefficienten för det Rademacher-Walsh spektrumet av n-variabeln och funktionen för en viss tilldelning som bestämmer rotations vinkeln.

## <a name="input"></a>Indata

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Inmatad tilldelning som heltal (från 0 till 2 ^ n-1)



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

