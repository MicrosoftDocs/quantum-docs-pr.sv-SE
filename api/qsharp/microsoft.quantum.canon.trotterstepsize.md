---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Funktionen TrotterStepSize
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204699"
---
# <a name="trotterstepsize-function"></a>Funktionen TrotterStepSize

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar Trotter steg storlek i rekursiv implementering av algoritmen för simulering av Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Indata

### <a name="order--int"></a>ordning: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Kommentarer

Den här åtgärden använder en annan index konvention än för [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). Motsvarar i synnerhet `DecomposedIntoTimeStepsCA(_, 4)` den skalära $p _2 (\lambda) $ i Quant-pH/0508139.