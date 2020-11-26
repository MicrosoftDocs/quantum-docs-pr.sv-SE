---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Funktionen DecomposedOn
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203237"
---
# <a name="decomposedon-function"></a>Funktionen DecomposedOn

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Deskapar en permutation för en variabel

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Beskrivning

Gett en permutation $ \pi $ ( `perm` ) och ett index $i $ ( `index` ), den här metoden returnerar tre permutationer $ ((\ pi_l, \ pi_r), \pi ') $ så att avbildningarna av $ \ pi_l $ och $ \ pi_r $ inte ändrar bitar i deras element i andra index än $i $ och bilder av $ \pi $ ändra inte bit $i $ i sina element.

## <a name="input"></a>Indata

### <a name="perm--int"></a>behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Utdata: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

