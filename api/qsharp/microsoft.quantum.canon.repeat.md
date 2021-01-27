---
uid: Microsoft.Quantum.Canon.Repeat
title: Upprepa åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852248"
---
# <a name="repeat-operation"></a>Upprepa åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Upprepar en åtgärd ett angivet antal gånger.

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Indata

### <a name="op--tinput--unit"></a>OP: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Åtgärden som ska anropas upprepade gånger.


### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger som ska anropas `op` .


### <a name="input--tinput"></a>inmatade: ' TInput

Inpasset som ska skickas till `op` .



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="tinput"></a>'TInput



## <a name="example"></a>Exempel

Följande är likvärdiga:

```qsharp
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. Quantum. Canon. Repeata](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. Quantum. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. Quantum. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)