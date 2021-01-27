---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kodad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855483"
---
# <a name="encoded-function"></a>Kodad funktion

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Koda sanningen-tabellen i {1,-1} kodning

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>Indata

### <a name="table--bool"></a>Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Sanningen-tabell som en matris med sanningen-värden



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

Sanningen-tabell som matris med {1,-1} heltal

## <a name="example"></a>Exempel

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```