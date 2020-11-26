---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203951"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString funktion

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Beräknar Z-komponenten i Jordanien – Wigner sträng mellan fermion-index i en fermionic-operator med ett jämnt antal skapande/Annihilation-operatörer.

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>Indata

### <a name="nfermions--int"></a>nFermions: [int](xref:microsoft.quantum.lang-ref.int)

Antalet Fermions i systemet.


### <a name="idxfermions--int"></a>idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]

fermionic operatörs index.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bitstring `Bool[]` `true` där a `PauliZ` ska användas.