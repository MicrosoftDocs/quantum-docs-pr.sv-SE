---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: Funktionen DumpMachine
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727288"
---
# <a name="dumpmachine-function"></a>Funktionen DumpMachine

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Dumpar den aktuella mål datorns status.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Indata

### <a name="location--t"></a>plats: ' t '

Innehåller information om var datorns dump ska genereras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

Inga.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Med den här metoden kan du dumpa information om mål datorns aktuella status till en fil eller någon annan plats.
Den faktiska informationen som genereras och semantiken för `location` är specifika för varje måldator. Men att ange en tom tupel som en plats ( `()` ) eller utesluta `location` parametern vanligt vis innebär att du genererar utdata till-konsolen.

För att den lokala fullständiga tillstånds simulatorn ska distribueras som en del av Quantum Development Kit förväntar den här metoden en sträng med sökvägen till en fil där den skriver vågen som en endimensionell matris med komplexa tal, där varje element representerar amplituderna för sannolikheten för att mäta motsvarande tillstånd.