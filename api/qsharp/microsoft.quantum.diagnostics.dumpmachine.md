---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: Funktionen DumpMachine
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853410"
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