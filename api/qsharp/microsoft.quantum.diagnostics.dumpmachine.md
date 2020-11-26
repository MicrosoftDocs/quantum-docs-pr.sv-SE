---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: Funktionen DumpMachine
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202115"
---
# <a name="dumpmachine-function"></a>Funktionen DumpMachine

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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