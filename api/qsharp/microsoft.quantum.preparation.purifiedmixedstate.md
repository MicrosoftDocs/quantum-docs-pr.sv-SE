---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: Funktionen PurifiedMixedState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854292"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="e88ef-102">Funktionen PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="e88ef-102">PurifiedMixedState function</span></span>

<span data-ttu-id="e88ef-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e88ef-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e88ef-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e88ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e88ef-105">Returnerar en åtgärd som förbereder en rening av ett blandat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e88ef-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="e88ef-106">Ett "renat blandat tillstånd" syftar på tillstånd i formatet | ψ ⟩ = Σi √ Pi | i ⟩ | garbagei ⟩ som anges av en Vector of koefficienter {PI}.</span><span class="sxs-lookup"><span data-stu-id="e88ef-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="e88ef-107">Tillstånd för detta formulär kan minskas till blandade tillstånd ρ ≔ Pi | i ⟩ ⟨ i | genom att spåra "skräp"-registret (det vill säga ett blandat läge som är diagonalt i beräknings basen).</span><span class="sxs-lookup"><span data-stu-id="e88ef-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="e88ef-108">Se https://arxiv.org/pdf/1805.03662.pdf?page=15 för ytterligare diskussion.</span><span class="sxs-lookup"><span data-stu-id="e88ef-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="e88ef-109">Description</span><span class="sxs-lookup"><span data-stu-id="e88ef-109">Description</span></span>

<span data-ttu-id="e88ef-110">Använder den Quantum-ROM-teknik som representerar en specifik densitet, som returnerar denna representation som en åtgärd för förberedelse av tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e88ef-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="e88ef-111">I synnerhet en lista över $N $ koefficienter $ \ alpha_j $, den här funktionen returnerar en åtgärd som använder en Quantum-ROM-teknik för att förbereda en uppskattning $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ av det blandade tillstånd $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ där varje $p _j $ är en approximation till den aktuella koefficienten $ \ alpha_j $, t. ex. $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ för varje $j $.</span><span class="sxs-lookup"><span data-stu-id="e88ef-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="e88ef-112">När du godkände ett index register och ett register över skräp qubits från början i tillstånd $ \ket {0} \ket{00\cdots 0} förbereder den returnerade åtgärden båda registren i reningen av $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, så att återställning och avallokerar skräp registreringen fungerar som den önskade förberedelsen i mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e88ef-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="e88ef-113">Indata</span><span class="sxs-lookup"><span data-stu-id="e88ef-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e88ef-114">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e88ef-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e88ef-115">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e88ef-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="e88ef-116">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e88ef-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e88ef-117">Matris med $N $-koefficienter som anger sannolikheten för bas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e88ef-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="e88ef-118">Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="e88ef-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="e88ef-119">Utdata: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="e88ef-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="e88ef-120">En åtgärd som förbereder $ \tilde \rho $ som en rening på ett gemensamt index och skräp registrering.</span><span class="sxs-lookup"><span data-stu-id="e88ef-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="e88ef-121">Exempel</span><span class="sxs-lookup"><span data-stu-id="e88ef-121">Example</span></span>

<span data-ttu-id="e88ef-122">Följande kodfragment förbereder en rening av $3 $-qubit State $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, där $ \vec\alpha = (1,0, 2,0, 3,0, 4,0, 5,0) $ och mål felet är $10 ^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="e88ef-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="e88ef-123">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e88ef-123">Remarks</span></span>

<span data-ttu-id="e88ef-124">De koefficienter som anges för den här åtgärden är normaliserade efter 1 – normal, så att koefficienterna alltid anses som beskriver en giltig kategoriska-sannolikhets fördelning.</span><span class="sxs-lookup"><span data-stu-id="e88ef-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="e88ef-125">Referenser</span><span class="sxs-lookup"><span data-stu-id="e88ef-125">References</span></span>

- <span data-ttu-id="e88ef-126">Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e88ef-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="e88ef-127">Se även</span><span class="sxs-lookup"><span data-stu-id="e88ef-127">See Also</span></span>

- [<span data-ttu-id="e88ef-128">Microsoft. Quantum. preparation. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="e88ef-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)