---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: Funktionen NearEqualityFactCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 95364541adfa1dc57b1f147c3992c9fd9f5f6c68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201571"
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

