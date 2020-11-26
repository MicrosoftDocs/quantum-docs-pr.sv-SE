---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221716"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar ordnings elementen i en matris som måste växlas för att skapa en ordnad matris.
Förutsätter att växlingar sker på plats.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Indata

### <a name="neworder--int"></a>newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Matris med permutationen av index för den nya matrisen. Det bör finnas $n $ Elements, var och en är ett unikt heltal från $0 $ till $n-$1.



## <a name="output--intint"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tuppeln representerar de två index som ska växlas. Växlingarna börjar vid det lägsta indexet.

## <a name="remarks"></a>Kommentarer

## <a name="psuedocode"></a>Psuedocode

för (index i 0.. längd (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] med newOrder [newOrder [index]]}}