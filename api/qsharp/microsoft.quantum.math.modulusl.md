---
uid: Microsoft.Quantum.Math.ModulusL
title: Modulus-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194941"
---
# <a name="modulusl-function"></a>Modulus-funktion

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar de kanoniska resterna av `value` modulo `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Indata

### <a name="value--bigint"></a>värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Värdet för vilken restsubstanser beräknas


### <a name="modulus--bigint"></a>Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Den modul som rester tar emot måste vara positiva



## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Heltal $r $ mellan 0 och `modulus - 1` som `value - r` är delbar med modulus

## <a name="remarks"></a>Kommentarer

Den här funktionen fungerar annorlunda för hur operatorn `%` beter sig i C# och Q # som i resultatet är alltid ett positivt heltal mellan 0 och `modulus - 1` , även om värdet är negativt.