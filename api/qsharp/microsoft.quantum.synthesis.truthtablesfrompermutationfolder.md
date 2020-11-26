---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Funktionen TruthTablesFromPermutationFolder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231032"
---
# <a name="truthtablesfrompermutationfolder-function"></a>Funktionen TruthTablesFromPermutationFolder

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Diskompositions logik för ett enda variabel index

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>Beskrivning

Detta tar det aktuella läget och genererar en uppdaterad permutation och eventuellt lägger till nya funktioner för kontrollerade portar.

## <a name="input"></a>Indata

### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>tillstånd: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>Utdata: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

