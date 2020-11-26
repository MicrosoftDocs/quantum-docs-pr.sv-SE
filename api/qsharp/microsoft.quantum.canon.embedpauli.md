---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Funktionen EmbedPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207045"
---
# <a name="embedpauli-function"></a>Funktionen EmbedPauli

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en enda-qubit Pauli-operator och indexet för en qubit returneras en Pauli-operator med en med en-operator med den aktuella indexen och `PauliI` vid alla andra index.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Indata

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

En qubit Pauli-operatör som ska placeras på den aktuella platsen.


### <a name="location--int"></a>plats: [int](xref:microsoft.quantum.lang-ref.int)

Ett index som `output[location] == pauli` , där `output` är resultatet av den här funktionen.


### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Längden på matrisen som ska returneras.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

