---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Funktionen DecomposedOn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855518"
---
# <a name="decomposedon-function"></a>Funktionen DecomposedOn

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Deskapar en permutation för en variabel

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Description

Gett en permutation $ \pi $ ( `perm` ) och ett index $i $ ( `index` ), den här metoden returnerar tre permutationer $ ((\ pi_l, \ pi_r), \pi ') $ så att avbildningarna av $ \ pi_l $ och $ \ pi_r $ inte ändrar bitar i deras element i andra index än $i $ och bilder av $ \pi $ ändra inte bit $i $ i sina element.

## <a name="input"></a>Indata

### <a name="perm--int"></a>behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Utdata: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Exempel

Anta att indata är perm = [0, 2, 3, 5, 7, 1, 4, 6] och index = 0, beräknar den här funktionen tre permutationer baserat på följande tabell, som visar permutationen `perm` i binär notation med element i grupp A och bilder i grupp D.  Kolumnerna listar bit indexen.

|   En |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Alla värden för index som inte är lika med 0 (= index) kopieras från A till B och från D till C.

|   En |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Nästa 0 placeras för det första elementet med ett tomt index i kolumn 0 i Block B och därefter placeras en 1 i B där prefixet matchar (i det första fallet den andra raden med index 0 0).
Efteråt läggs en 1 till i samma rad i block C, och sedan 0 för motsvarande prefix i block C.  Den här processen upprepas tills alla index har placerats i kolumn 0 i Block B och C.

|   En |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

Vi kan läsa tre nya permutationer från tabellen:

- $ \ pi_l $ med element i A, bilder i B (vänster)
- $ \ pi_r $ med element i D, bilder i C (höger)
- $ \pi $ med element i B, bilder i C (rest)

Observera att eftersom design bit värden inte ändras i $ \ pi_l $ och $ \ pi_r $ för index 1 och 2, och bit värdena inte ändras för i $ \ pi_ $ för index 0.  Observera också att $ \ pi_l $ och $ \ pi_r $ måste vara inversen.

De härledda och returnerade permutationerna är: Left = [0, 1, 2, 3, 4, 6, 7] höger = [0, 1, 3, 2, 4, 5, 7, 6] rest = [0, 3, 2, 5, 6, 1, 4, 7]