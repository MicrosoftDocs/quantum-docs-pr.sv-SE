---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Funktionen ControlledOnInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840790"
---
# <a name="controlledonint-function"></a>Funktionen ControlledOnInt

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en enhetlig operator som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar ett angivet positivt heltal.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Positivt heltal.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Enhetlig operatör.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En enhetlig operatör som gäller `oracle` för mål registret om kontroll registerets tillstånd motsvarar nummer tillstånd `numberState` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Värdet för `numberState` tolkas med en lite-endian-kodning.