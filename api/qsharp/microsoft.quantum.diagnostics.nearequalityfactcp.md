---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: Funktionen NearEqualityFactCP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 477449913732950ad26adc0cdabaaaab803a20c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853288"
---
# <a name="nearequalityfactcp-function"></a>Funktionen NearEqualityFactCP

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Garanterar att ett klassiskt komplext tal har det förväntade värdet upp till en liten tolerans för 1e-10.

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--complexpolar"></a>faktiskt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Det tal som ska kontrol leras.


### <a name="expected--complexpolar"></a>förväntat: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Det förväntade värdet.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

