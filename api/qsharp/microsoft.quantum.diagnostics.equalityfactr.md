---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Funktionen EqualityFactR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727231"
---
# <a name="equalityfactr-function"></a>Funktionen EqualityFactR

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


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

