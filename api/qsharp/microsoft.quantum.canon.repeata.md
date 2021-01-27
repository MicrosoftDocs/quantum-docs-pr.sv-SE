---
uid: Microsoft.Quantum.Canon.RepeatA
title: Upprepa åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852225"
---
# <a name="repeata-operation"></a>Upprepa åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Upprepar en åtgärd ett angivet antal gånger.

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a>Indata

### <a name="op--tinput--unit--is-adj"></a>OP: ' TInput => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

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
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. Quantum. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. Quantum. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)