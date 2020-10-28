---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Funktionen PauliArrayAsInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727501"
---
# <a name="pauliarrayasint-function"></a>Funktionen PauliArrayAsInt

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paketfilerna [](https://nuget.org/packages/)


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