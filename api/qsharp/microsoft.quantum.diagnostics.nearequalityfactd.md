---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: Funktionen NearEqualityFactD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727192"
---
# <a name="nearequalityfactd-function"></a>Funktionen NearEqualityFactD

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Garanterar att ett klassiskt flytt ALS värde har det förväntade värdet upp till en liten tolerans för 1e-10.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--double"></a>faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det tal som ska kontrol leras.


### <a name="expected--double"></a>förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det förväntade värdet.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Detta motsvarar <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> med hårdkodad tolerans på $10 ^ {-10} $.