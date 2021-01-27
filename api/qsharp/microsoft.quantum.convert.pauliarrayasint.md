---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Funktionen PauliArrayAsInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832713"
---
# <a name="pauliarrayasint-function"></a>Funktionen PauliArrayAsInt

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Kodar en qubit Pauli-operatör som representeras som en matris med qubit Pauli-operatörer till ett heltal.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Indata

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En matris med högst 31 Single-qubit Pauli-operatörer.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal som identifierar unikt `paulis` , enligt beskrivningen nedan.

## <a name="remarks"></a>Kommentarer

Varje Pauli-operatör kan kodas med två bitar: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

Med en matris med Pauli `[P0, ..., Pn]` -operatörer returnerar den här funktionen ett heltal med binär expansion som bildas genom att sammanfoga mappningarna för varje Pauli-operator i big-endian-ordningen `bits(Pn) ... bits(P0)` .