---
uid: Microsoft.Quantum.Canon.Angle
title: Funktionen vinkel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729763"
---
# <a name="angle-function"></a>Funktionen vinkel

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Returnerar 1, om `index` har ett udda antal 1s och-1, om `index` har ett jämnt antal 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Beskrivning

Värdet motsvarar tecknet för koefficienten för det Rademacher-Walsh spektrumet av n-variabeln och funktionen för en viss tilldelning som bestämmer rotations vinkeln.

## <a name="input"></a>Indata

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Inmatad tilldelning som heltal (från 0 till 2 ^ n-1)



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

