---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Funktionen AllEqualityFactI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727372"
---
# <a name="allequalityfacti-function"></a>Funktionen AllEqualityFactI

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Förutsätter att två matriser med heltals värden är lika.

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--int"></a>faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrisen som produceras av ett test fall av intresse.


### <a name="expected--int"></a>förväntat: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrisen som förväntas från ett test fall av intresse.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Ett meddelande som ska skrivas ut om matriserna inte är lika.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

