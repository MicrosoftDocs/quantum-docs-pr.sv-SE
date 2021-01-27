---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829788"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Förutsätter att en qubit förväntas i det förväntade läget.

`expected` representerar en komplex Vector, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
Det första elementet i tuppeln som representerar var och en av $a $, $b $ är den reella delen av det komplexa talet, medan det andra är den imaginära delen.
Det sista argumentet definierar toleransen för vilken kontroll görs.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Indata

### <a name="expected--complexcomplex"></a>förväntad: ([komplex](xref:Microsoft.Quantum.Math.Complex),[komplex](xref:Microsoft.Quantum.Math.Complex))

Förväntade komplexa amplituder för $ \ket {0} $ respektive $ \ket {1} $.


### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit vars tillstånd ska försäkras. Observera att denna qubit antas vara en avgränsad från andra allokerade qubits och inte Entangled.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Den avvikande toleransen enligt vilken faktiska amplituder får avvika från förväntat värde.
Se anmärkningar nedan för mer information.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>Kommentarer

Följande Mathematica-kod kan användas för att verifiera uttryck för mi, MX, My, MZ:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

Toleransen är $L \_ {\infty} $-avståndet mellan 3 dimensionella verkliga vektorer (x ₂, x-₃, x-₄) som definieras av $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ och verklig Vector (y ₂, y ₃, y ₄) definieras av ρ = Y ₁ I + y ₂ x + y ₃ Y + y ₄ Z där ρ är densiteten som motsvarar status för registret.
Detta gäller endast under antagandet att TR (ρ) och tr (| ψ ⟩ ⟨ ψ |) är båda 1 (t. ex. x ₁ = 1/2, y ₁ = 1/2).
Om detta inte är fallet, förutsätter funktionen att l ∞ avståndet mellan (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) och (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) är mindre än tolerans parametern.