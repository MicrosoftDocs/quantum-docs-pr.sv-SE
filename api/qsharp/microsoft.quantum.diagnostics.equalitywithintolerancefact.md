---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Funktionen EqualityWithinToleranceFact
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727234"
---
# <a name="equalitywithintolerancefact-function"></a>Funktionen EqualityWithinToleranceFact

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Representerar anspråket att ett klassiskt flytt ALS värde har det förväntade värdet upp till en viss absolut tolerans.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--double"></a>faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det tal som ska kontrol leras.


### <a name="expected--double"></a>förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det förväntade värdet.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

