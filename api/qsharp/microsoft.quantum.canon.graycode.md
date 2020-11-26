---
uid: Microsoft.Quantum.Canon.GrayCode
title: Funktionen GrayCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206892"
---
# <a name="graycode-function"></a>Funktionen GrayCode

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar grå kod sekvenser

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Indata

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Antal bitar



## <a name="output--intint"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Matris med tupler. Det första värdet i tuppeln är ett värde i GrayCode-sekvensens andra värde i tuppeln är positionen att ändra i det aktuella värdet för att hämta nästa.