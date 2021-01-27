---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fakta funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853313"
---
# <a name="fact-function"></a>Fakta funktion

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Deklarerar att ett klassiskt villkor är sant.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--bool"></a>faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)

Villkoret som ska deklareras.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Fel meddelande strängen som ska skrivas ut om klassiskt villkor är falskt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

Följande Q #-kodfragment kommer att Miss Missing:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. motstridighet](xref:Microsoft.Quantum.Diagnostics.Contradiction)