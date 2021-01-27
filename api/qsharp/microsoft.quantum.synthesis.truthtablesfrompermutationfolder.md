---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Funktionen TruthTablesFromPermutationFolder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 881bb8e29d3d7761cc521837502ea79b0714b381
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855257"
---
# <a name="truthtablesfrompermutationfolder-function"></a>Funktionen TruthTablesFromPermutationFolder

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Diskompositions logik för ett enda variabel index

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>Description

Detta tar det aktuella läget och genererar en uppdaterad permutation och eventuellt lägger till nya funktioner för kontrollerade portar.

## <a name="input"></a>Indata

### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>tillstånd: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>Utdata: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

