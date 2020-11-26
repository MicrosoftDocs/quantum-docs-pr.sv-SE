---
uid: Microsoft.Quantum.Canon.Angle
title: Funktionen vinkel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219421"
---
# <a name="angle-function"></a>Funktionen vinkel

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

