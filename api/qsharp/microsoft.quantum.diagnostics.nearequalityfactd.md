---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: Funktionen NearEqualityFactD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827898"
---
# <a name="nearequalityfactd-function"></a>Funktionen NearEqualityFactD

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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