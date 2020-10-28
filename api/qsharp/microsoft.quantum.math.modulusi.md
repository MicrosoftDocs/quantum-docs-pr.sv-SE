---
uid: Microsoft.Quantum.Math.ModulusI
title: Modulus-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732699"
---
# <a name="modulusi-function"></a>Modulus-funktion

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


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

Den här funktionen fungerar annorlunda för hur operatorn `%` beter sig i C# och Q # som i resultatet är alltid ett positivt heltal mellan 0 och `modulus - 1` , även om värdet är negativt.