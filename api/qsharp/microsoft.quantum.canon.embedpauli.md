---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Funktionen EmbedPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840525"
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



## <a name="example"></a>Exempel

Så här hämtar du matrisen `[PauliI, PauliI, PauliX, PauliI]` :

```qsharp
EmbedPauli(PauliX, 2, 3);
```