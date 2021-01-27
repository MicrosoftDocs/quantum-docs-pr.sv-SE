---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852395"
---
# <a name="noop-operation"></a>NoOp-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Utför identitets åtgärden (inga-OP) i ett argument.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Den här åtgärden tar ett värde av valfri typ och gör ingenting.
Detta kan vara användbart när en indatatyp av en åtgärds typ förväntas, men ingen åtgärd vidtas.
Om till exempel en viss fel korrigering Syndrome anger att det inte har uppstått något fel, `NoOp<Qubit[]>` kan det vara rätt återställnings förfarande.
Om en åtgärd till exempel förväntar sig en tillstånds förberedelse procedur som inmatare, `NoOp<Qubit[]>` kan användas för att förbereda status $ \ket{0 \cdots 0} $.

## <a name="input"></a>Indata

### <a name="input--t"></a>inmatade: ' t

Ett värde som ska ignoreras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

I nästan alla fall måste typ parametern för `NoOp` anges explicit. Är till exempel `NoOp<Qubit>` identiskt med <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. inbyggt.](xref:Microsoft.Quantum.Intrinsic.I)