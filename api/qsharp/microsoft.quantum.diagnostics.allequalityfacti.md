---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Funktionen AllEqualityFactI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830893"
---
# <a name="allequalityfacti-function"></a>Funktionen AllEqualityFactI

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

