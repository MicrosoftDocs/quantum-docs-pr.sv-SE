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
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="b4765-102">AssertQubitIsInStateWithinTolerance-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b4765-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="b4765-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b4765-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b4765-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b4765-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b4765-105">Förutsätter att en qubit förväntas i det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="b4765-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="b4765-106">`expected` representerar en komplex Vector, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="b4765-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="b4765-107">Det första elementet i tuppeln som representerar var och en av $a $, $b $ är den reella delen av det komplexa talet, medan det andra är den imaginära delen.</span><span class="sxs-lookup"><span data-stu-id="b4765-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="b4765-108">Det sista argumentet definierar toleransen för vilken kontroll görs.</span><span class="sxs-lookup"><span data-stu-id="b4765-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="b4765-109">Indata</span><span class="sxs-lookup"><span data-stu-id="b4765-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="b4765-110">förväntad: ([komplex](xref:Microsoft.Quantum.Math.Complex),[komplex](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="b4765-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="b4765-111">Förväntade komplexa amplituder för $ \ket {0} $ respektive $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="b4765-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b4765-112">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b4765-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b4765-113">Qubit vars tillstånd ska försäkras.</span><span class="sxs-lookup"><span data-stu-id="b4765-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="b4765-114">Observera att denna qubit antas vara en avgränsad från andra allokerade qubits och inte Entangled.</span><span class="sxs-lookup"><span data-stu-id="b4765-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b4765-115">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b4765-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b4765-116">Den avvikande toleransen enligt vilken faktiska amplituder får avvika från förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="b4765-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="b4765-117">Se anmärkningar nedan för mer information.</span><span class="sxs-lookup"><span data-stu-id="b4765-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4765-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4765-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="b4765-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="b4765-119">Example</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b4765-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b4765-120">Remarks</span></span>

<span data-ttu-id="b4765-121">Följande Mathematica-kod kan användas för att verifiera uttryck för mi, MX, My, MZ:</span><span class="sxs-lookup"><span data-stu-id="b4765-121">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

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

<span data-ttu-id="b4765-122">Toleransen är $L \_ {\infty} $-avståndet mellan 3 dimensionella verkliga vektorer (x ₂, x-₃, x-₄) som definieras av $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ och verklig Vector (y ₂, y ₃, y ₄) definieras av ρ = Y ₁ I + y ₂ x + y ₃ Y + y ₄ Z där ρ är densiteten som motsvarar status för registret.</span><span class="sxs-lookup"><span data-stu-id="b4765-122">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="b4765-123">Detta gäller endast under antagandet att TR (ρ) och tr (| ψ ⟩ ⟨ ψ |) är båda 1 (t. ex. x ₁ = 1/2, y ₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="b4765-123">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="b4765-124">Om detta inte är fallet, förutsätter funktionen att l ∞ avståndet mellan (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) och (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) är mindre än tolerans parametern.</span><span class="sxs-lookup"><span data-stu-id="b4765-124">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>