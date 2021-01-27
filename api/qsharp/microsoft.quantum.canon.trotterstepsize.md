---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Funktionen TrotterStepSize
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840078"
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