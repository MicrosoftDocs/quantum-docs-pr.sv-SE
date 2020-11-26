---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: Funktionen PurifiedMixedStateWithData
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229961"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="7e925-102">Funktionen PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="7e925-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="7e925-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7e925-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7e925-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e925-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e925-105">Returnerar en åtgärd som förbereder en rening av ett blandat tillstånd, Entangled med ett register som representerar en specifik samling data.</span><span class="sxs-lookup"><span data-stu-id="7e925-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="7e925-106">Ett "rena blandat tillstånd med data" syftar på ett tillstånd för formatet Σi √ Pi | i ⟩ | XI ⟩ | garbagei ⟩ där varje XI är en bitstring som innehåller ytterligare data som är kopplade till registret | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="7e925-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="7e925-107">Se https://arxiv.org/pdf/1805.03662.pdf?page=15 för ytterligare diskussion.</span><span class="sxs-lookup"><span data-stu-id="7e925-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="7e925-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e925-108">Description</span></span>

<span data-ttu-id="7e925-109">Använder den Quantum-ROM-teknik som representerar en specifik densitet, som returnerar denna representation som en åtgärd för förberedelse av tillstånd.</span><span class="sxs-lookup"><span data-stu-id="7e925-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="7e925-110">I synnerhet en lista över $N $ koefficienter $ \ alpha_j $ och en bitstring $ \vec{x}_j $ som är associerad med respektive koefficient. den här funktionen returnerar en åtgärd som använder Quantum-Rom-tekniken för att förbereda en ungefärlig $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ av blandat tillstånd $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $ där varje $p _j $ är en uppskattning av den aktuella koefficienten $ \ alpha_j $, t. ex. $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ för varje $j $.</span><span class="sxs-lookup"><span data-stu-id="7e925-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="7e925-111">När du godkände ett index register och ett register över skräp qubits, inlednings vis i status $ \ket {0} \ket{00\cdots 0}, den returnerade åtgärden förbereder båda registren i reningen av $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $ så att att återställa och avallokera skräp registreringen är den önskade förberedelsen i mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="7e925-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="7e925-112">Indata</span><span class="sxs-lookup"><span data-stu-id="7e925-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="7e925-113">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7e925-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7e925-114">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="7e925-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="7e925-115">koefficienter: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="7e925-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="7e925-116">Matris med $N $-koefficienter som anger sannolikheten för grund tillstånd, tillsammans med bitstring $ \vec{x} _j $ som är associerad med respektive koefficient.</span><span class="sxs-lookup"><span data-stu-id="7e925-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="7e925-117">Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="7e925-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="7e925-118">Utdata: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="7e925-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="7e925-119">En åtgärd som förbereder $ \tilde \rho $ som en rening på ett gemensamt index och skräp registrering.</span><span class="sxs-lookup"><span data-stu-id="7e925-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e925-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7e925-120">Remarks</span></span>

<span data-ttu-id="7e925-121">De koefficienter som anges för den här åtgärden är normaliserade efter 1 – normal, så att koefficienterna alltid anses som beskriver en giltig kategoriska-sannolikhets fördelning.</span><span class="sxs-lookup"><span data-stu-id="7e925-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="7e925-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="7e925-122">References</span></span>

- <span data-ttu-id="7e925-123">Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="7e925-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="7e925-124">Se även</span><span class="sxs-lookup"><span data-stu-id="7e925-124">See Also</span></span>

- [<span data-ttu-id="7e925-125">Microsoft. Quantum. preparation. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="7e925-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)