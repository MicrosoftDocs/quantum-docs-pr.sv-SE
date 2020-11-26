---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: Funktionen PurifiedMixedState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230029"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="e5543-102">Funktionen PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="e5543-102">PurifiedMixedState function</span></span>

<span data-ttu-id="e5543-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e5543-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e5543-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5543-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5543-105">Returnerar en åtgärd som förbereder en rening av ett blandat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e5543-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="e5543-106">Ett "renat blandat tillstånd" syftar på tillstånd i formatet | ψ ⟩ = Σi √ Pi | i ⟩ | garbagei ⟩ som anges av en Vector of koefficienter {PI}.</span><span class="sxs-lookup"><span data-stu-id="e5543-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="e5543-107">Tillstånd för detta formulär kan minskas till blandade tillstånd ρ ≔ Pi | i ⟩ ⟨ i | genom att spåra "skräp"-registret (det vill säga ett blandat läge som är diagonalt i beräknings basen).</span><span class="sxs-lookup"><span data-stu-id="e5543-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="e5543-108">Se https://arxiv.org/pdf/1805.03662.pdf?page=15 för ytterligare diskussion.</span><span class="sxs-lookup"><span data-stu-id="e5543-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="e5543-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e5543-109">Description</span></span>

<span data-ttu-id="e5543-110">Använder den Quantum-ROM-teknik som representerar en specifik densitet, som returnerar denna representation som en åtgärd för förberedelse av tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e5543-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="e5543-111">I synnerhet en lista över $N $ koefficienter $ \ alpha_j $, den här funktionen returnerar en åtgärd som använder en Quantum-ROM-teknik för att förbereda en uppskattning $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ av det blandade tillstånd $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ där varje $p _j $ är en approximation till den aktuella koefficienten $ \ alpha_j $, t. ex. $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ för varje $j $.</span><span class="sxs-lookup"><span data-stu-id="e5543-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="e5543-112">När du godkände ett index register och ett register över skräp qubits från början i tillstånd $ \ket {0} \ket{00\cdots 0} förbereder den returnerade åtgärden båda registren i reningen av $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, så att återställning och avallokerar skräp registreringen fungerar som den önskade förberedelsen i mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e5543-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="e5543-113">Indata</span><span class="sxs-lookup"><span data-stu-id="e5543-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e5543-114">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5543-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5543-115">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e5543-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="e5543-116">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e5543-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e5543-117">Matris med $N $-koefficienter som anger sannolikheten för bas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e5543-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="e5543-118">Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="e5543-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="e5543-119">Utdata: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="e5543-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="e5543-120">En åtgärd som förbereder $ \tilde \rho $ som en rening på ett gemensamt index och skräp registrering.</span><span class="sxs-lookup"><span data-stu-id="e5543-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5543-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e5543-121">Remarks</span></span>

<span data-ttu-id="e5543-122">De koefficienter som anges för den här åtgärden är normaliserade efter 1 – normal, så att koefficienterna alltid anses som beskriver en giltig kategoriska-sannolikhets fördelning.</span><span class="sxs-lookup"><span data-stu-id="e5543-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="e5543-123">Referenser</span><span class="sxs-lookup"><span data-stu-id="e5543-123">References</span></span>

- <span data-ttu-id="e5543-124">Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e5543-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="e5543-125">Se även</span><span class="sxs-lookup"><span data-stu-id="e5543-125">See Also</span></span>

- [<span data-ttu-id="e5543-126">Microsoft. Quantum. preparation. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="e5543-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)