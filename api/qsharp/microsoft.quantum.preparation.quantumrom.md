---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Funktionen QuantumROM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732622"
---
# <a name="quantumrom-function"></a><span data-ttu-id="f093c-102">Funktionen QuantumROM</span><span class="sxs-lookup"><span data-stu-id="f093c-102">QuantumROM function</span></span>

<span data-ttu-id="f093c-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f093c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f093c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f093c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f093c-105">Använder Quantum ROM-tekniken för att representera en bestämd densitet.</span><span class="sxs-lookup"><span data-stu-id="f093c-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="f093c-106">Med en lista med $N $ koefficienter $ \ alpha_j $, returnerar detta en enhetlig $U $ som använder Quantum-ROM-tekniken för att förbereda en uppskattning $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ av reningen av densitets mat ris $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="f093c-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="f093c-107">I den här uppskattningen är felet $ \epsilon $ sådant som $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ och $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="f093c-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="f093c-108">Med andra ord, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ ket {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="f093c-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="f093c-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f093c-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="f093c-110">Indata</span><span class="sxs-lookup"><span data-stu-id="f093c-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="f093c-111">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f093c-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f093c-112">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="f093c-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="f093c-113">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f093c-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f093c-114">Matris med $N $-koefficienter som anger sannolikheten för bas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="f093c-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="f093c-115">Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="f093c-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="f093c-116">Utdata: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL)</span><span class="sxs-lookup"><span data-stu-id="f093c-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="f093c-117">Första parametern</span><span class="sxs-lookup"><span data-stu-id="f093c-117">First parameter</span></span>

<span data-ttu-id="f093c-118">En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.</span><span class="sxs-lookup"><span data-stu-id="f093c-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="f093c-119">Andra parameter</span><span class="sxs-lookup"><span data-stu-id="f093c-119">Second parameter</span></span>

<span data-ttu-id="f093c-120">Den enpresterande $ \ sum_j | \ alpha_j | $ för den effektiva matrisen.</span><span class="sxs-lookup"><span data-stu-id="f093c-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="f093c-121">Tredje parametern</span><span class="sxs-lookup"><span data-stu-id="f093c-121">Third parameter</span></span>

<span data-ttu-id="f093c-122">Den enhetliga $U $.</span><span class="sxs-lookup"><span data-stu-id="f093c-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="f093c-123">Referenser</span><span class="sxs-lookup"><span data-stu-id="f093c-123">References</span></span>

- <span data-ttu-id="f093c-124">Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="f093c-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>