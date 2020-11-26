---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230097"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar en enhetlig överplacering över tillstånd som kodar 0 till `nIndices - 1` .

Det vill säga den här enhetliga $U $ skapar en enhetlig överplacering över alla nummer tillstånd $0 $ till $M-$1, med ingångs tillstånd $ \ket{0\cdots 0} $. Med andra ord, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

Det önskade antalet tillstånd $M $ i enhetlig överposition.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit-registret som lagrar nummer tillstånden i `LittleEndian` formatet.
Detta register måste kunna lagra numret $M-$1 och antas vara initierat i status $ \ket{0\cdots 0} $.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Åtgärden är adjointable men kräver att `indexRegister` är i ett enhetligt överplacerat tillstånd för de första `nIndices` bas tillstånden i detta fall.