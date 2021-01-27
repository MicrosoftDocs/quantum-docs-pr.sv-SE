---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Funktionen EqualityFactR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853333"
---
# <a name="equalityfactr-function"></a>Funktionen EqualityFactR

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förutsätter att en klassisk resultat variabel har det förväntade värdet.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--__invalidresult__"></a>faktiskt: __ogiltigt <Result>__

Den variabel som ska kontrol leras.


### <a name="expected--__invalidresult__"></a>förväntat: __ogiltigt <Result>__

Det förväntade värdet.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Fel meddelande strängen som ska användas när kontrollen utlöses.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

