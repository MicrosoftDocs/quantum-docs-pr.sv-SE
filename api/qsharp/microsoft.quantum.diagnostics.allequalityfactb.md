---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Funktionen AllEqualityFactB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727375"
---
# <a name="allequalityfactb-function"></a>Funktionen AllEqualityFactB

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


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

