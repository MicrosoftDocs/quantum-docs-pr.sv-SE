---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Funktionen FormattedFailure
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828283"
---
# <a name="formattedfailure-function"></a>Funktionen FormattedFailure

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Intern funktion som används för att rapportera fel i meningsfulla fel meddelanden.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--t"></a>faktiskt: ' t




### <a name="expected--t"></a>förväntat: ' t




### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Den här funktionen är avsedd att emuleras av simulerings körningar, så att du kan tillåta vidarebefordrande motstridiga ändringar.