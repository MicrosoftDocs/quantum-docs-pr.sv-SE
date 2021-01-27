---
uid: Microsoft.Quantum.Canon.GrayCode
title: Funktionen GrayCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840504"
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

## <a name="example"></a>Exempel

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```