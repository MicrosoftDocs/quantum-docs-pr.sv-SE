---
uid: Microsoft.Quantum.Math.ModulusI
title: Modulus-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847296"
---
# <a name="modulusi-function"></a>Modulus-funktion

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar de kanoniska resterna av `value` modulo `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Indata

### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Värdet för vilken restsubstanser beräknas


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Den modul som rester tar emot måste vara positiva



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Heltal $r $ mellan 0 och `modulus - 1` som `value - r` är delbar med modulus

## <a name="remarks"></a>Kommentarer

Den här funktionen fungerar annorlunda för hur operatorn `%` beter sig i C# och Q # som i resultatet är alltid ett icke-negativt heltal mellan 0 och `modulus - 1` , även om värdet är negativt.