---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Funktionen FormattedFailure
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727204"
---
# <a name="formattedfailure-function"></a>Funktionen FormattedFailure

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


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