---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Funktionen StatePreparationComplexCoefficients
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210377"
---
# <a name="statepreparationcomplexcoefficients-function"></a>Funktionen StatePreparationComplexCoefficients

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients är föråldrad. Använd <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> i stället.

Returnerar en åtgärd som förbereder ett bestämt Quantum-tillstånd.

Den returnerade åtgärden $U $ förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med komplexa koefficienter $r _j e ^ {i t_j} $ från $n $-qubit beräknings bas tillstånd $ \ket{0...0} $.

Åtgärden för U i ett nytilldelat register erhålls av $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="coefficients--complexpolar"></a>koefficienter: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matris med upp till $2 ^ n $ komplexa koefficienter som representeras av deras absoluta värde och fas $ (r_j, t_j) $. $J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL

En enhetlig åtgärd för tillstånds förberedelse $U $.

## <a name="remarks"></a>Kommentarer

Negativa ingångs-koefficienter $r _j < $0 behandlas som om det är positivt med värdet $ | r_j | $. `coefficients` fylls i med elementen $ (r_j, t_j) = (0,0, 0,0) $ om färre än $2 ^ n $ anges.