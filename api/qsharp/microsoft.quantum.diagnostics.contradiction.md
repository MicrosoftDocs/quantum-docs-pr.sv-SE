---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Motstridig funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727285"
---
# <a name="contradiction-function"></a>Motstridig funktion

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Deklarerar att ett klassiskt villkor är falskt.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--bool"></a>faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)

Villkoret som ska deklareras.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Fel meddelande strängen som ska skrivas ut om klassiskt villkor är sant.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. faktumet](xref:Microsoft.Quantum.Diagnostics.Fact)