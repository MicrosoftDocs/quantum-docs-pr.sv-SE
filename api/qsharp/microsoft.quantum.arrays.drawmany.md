---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210003"
---
# <a name="drawmany-operation"></a>DrawMany-åtgärd

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Upprepar en åtgärd för ett angivet antal exempel, och samlar in utdata i en matris.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Indata

### <a name="op--tinput--toutput"></a>OP: ' TInput => ' TOutput 

Åtgärden som ska anropas upprepade gånger.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Antal exempel som anropar `op` att samla in.


### <a name="input--tinput"></a>inmatade: ' TInput

Inpasset som ska skickas till `op` .



## <a name="output--toutput"></a>Utdata: ' TOutput []



## <a name="type-parameters"></a>Typparametrar

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)