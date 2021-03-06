---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: e2e4818e5d30b17dd1984c36da92d76b84403e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842391"
---
# <a name="preparearbitrarystate-operation"></a>PrepareArbitraryState-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareArbitraryState är föråldrad. Använd <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> i stället.

Med hänsyn till en uppsättning koefficienter och ett litet endian-kodat Quantum-register, förbereder ett tillstånd i detta register som beskrivs av de angivna koefficienterna.

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Den här åtgärden förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med komplexa koefficienter $r _j e ^ {i t_j} $ från $n $-qubit beräknings bas tillstånd $ \ket{0 \cdots 0} $.
I synnerhet kan åtgärden för den här åtgärden simuleras av en enhetlig omvandling $U $ som fungerar med status all – noll som

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Indata

### <a name="coefficients--complexpolar"></a>koefficienter: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matris med upp till $2 ^ n $ komplexa koefficienter som representeras av deras absoluta värde och fas $ (r_j, t_j) $. $J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit registrerar kodnings nummer tillstånd i litet endian-format. Detta förväntas bli initierat i beräknings grund tillstånd $ \ket{0...0} $.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Negativa ingångs-koefficienter $r _j < $0 behandlas som om det är positivt med värdet $ | r_j | $. `coefficients` fylls i med elementen $ (r_j, t_j) = (0,0, 0,0) $ om färre än $2 ^ n $ anges.

## <a name="references"></a>Referenser

- Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. preparation. ApproximatelyPrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)