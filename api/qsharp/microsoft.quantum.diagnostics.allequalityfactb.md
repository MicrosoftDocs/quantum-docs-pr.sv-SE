---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Funktionen AllEqualityFactB
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853547"
---
# <a name="allequalityfactb-function"></a>Funktionen AllEqualityFactB

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förutsätter att två matriser med booleska värden är lika.

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--bool"></a>faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matrisen som produceras av ett test fall av intresse.


### <a name="expected--bool"></a>förväntat: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matrisen som förväntas från ett test fall av intresse.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Ett meddelande som ska skrivas ut om matriserna inte är lika.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

