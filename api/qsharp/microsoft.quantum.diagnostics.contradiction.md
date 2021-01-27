---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Motstridig funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829371"
---
# <a name="contradiction-function"></a>Motstridig funktion

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>Exempel

Följande Q #-kod skriver ut "Hello, World":

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. faktumet](xref:Microsoft.Quantum.Diagnostics.Fact)