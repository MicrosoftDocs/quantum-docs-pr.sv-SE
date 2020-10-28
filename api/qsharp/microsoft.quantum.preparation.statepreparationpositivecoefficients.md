---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Funktionen StatePreparationPositiveCoefficients
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732587"
---
# <a name="statepreparationpositivecoefficients-function"></a>Funktionen StatePreparationPositiveCoefficients

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paketfilerna [](https://nuget.org/packages/)


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



## <a name="output--littleendian--unit-adj--ctl"></a>Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) just + CTL

En enhetlig åtgärd för tillstånds förberedelse $U $.

## <a name="remarks"></a>Kommentarer

Negativa ingångs-koefficienter $ \ alpha_j < $0 behandlas som om det är positivt med värdet $ | \ alpha_j | $. `coefficients` fylls i med elementen $ \ alpha_j = $0,0 om färre än $2 ^ n $ har angetts.