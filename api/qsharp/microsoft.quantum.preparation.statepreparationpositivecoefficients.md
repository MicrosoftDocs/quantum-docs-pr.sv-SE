---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Funktionen StatePreparationPositiveCoefficients
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193258"
---
# <a name="statepreparationpositivecoefficients-function"></a>Funktionen StatePreparationPositiveCoefficients

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationPositiveCoefficients är föråldrad. Använd <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> i stället.

Returnerar en åtgärd som förbereder angivet Quantum-tillstånd.

Den returnerade åtgärden $U $ förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med positiva koefficienter $ \ alpha_j \ge $0 från $n $-qubit beräknings bas tillstånd $ \ket{0...0} $.

Åtgärden för U i ett nytilldelat register erhålls av $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="coefficients--double"></a>koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

Matris med upp till $2 ^ n $ koefficienter $ \ alpha_j $. $J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL

En enhetlig åtgärd för tillstånds förberedelse $U $.

## <a name="remarks"></a>Kommentarer

Negativa ingångs-koefficienter $ \ alpha_j < $0 behandlas som om det är positivt med värdet $ | \ alpha_j | $. `coefficients` fylls i med elementen $ \ alpha_j = $0,0 om färre än $2 ^ n $ har angetts.