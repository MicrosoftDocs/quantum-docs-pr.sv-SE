---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Funktionen QuantumROM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229893"
---
# <a name="quantumrom-function"></a><span data-ttu-id="dc28c-102">Funktionen QuantumROM</span><span class="sxs-lookup"><span data-stu-id="dc28c-102">QuantumROM function</span></span>

<span data-ttu-id="dc28c-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="dc28c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="dc28c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc28c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="dc28c-105">QuantumROM är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="dc28c-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="dc28c-106">Använd <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> i stället.</span><span class="sxs-lookup"><span data-stu-id="dc28c-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="dc28c-107">Använder Quantum ROM-tekniken för att representera en bestämd densitet.</span><span class="sxs-lookup"><span data-stu-id="dc28c-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="dc28c-108">Med en lista med $N $ koefficienter $ \ alpha_j $, returnerar detta en enhetlig $U $ som använder Quantum-ROM-tekniken för att förbereda en uppskattning $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ av reningen av densitets mat ris $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="dc28c-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="dc28c-109">I den här uppskattningen är felet $ \epsilon $ sådant som $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ och $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="dc28c-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="dc28c-110">Med andra ord, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ ket {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="dc28c-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="dc28c-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dc28c-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="dc28c-112">Indata</span><span class="sxs-lookup"><span data-stu-id="dc28c-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="dc28c-113">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dc28c-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dc28c-114">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="dc28c-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="dc28c-115">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dc28c-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dc28c-116">Matris med $N $-koefficienter som anger sannolikheten för bas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="dc28c-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="dc28c-117">Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="dc28c-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="dc28c-118">Utdata: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL)</span><span class="sxs-lookup"><span data-stu-id="dc28c-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="dc28c-119">Första parametern</span><span class="sxs-lookup"><span data-stu-id="dc28c-119">First parameter</span></span>

<span data-ttu-id="dc28c-120">En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.</span><span class="sxs-lookup"><span data-stu-id="dc28c-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="dc28c-121">Andra parameter</span><span class="sxs-lookup"><span data-stu-id="dc28c-121">Second parameter</span></span>

<span data-ttu-id="dc28c-122">Den enpresterande $ \ sum_j | \ alpha_j | $ för den effektiva matrisen.</span><span class="sxs-lookup"><span data-stu-id="dc28c-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="dc28c-123">Tredje parametern</span><span class="sxs-lookup"><span data-stu-id="dc28c-123">Third parameter</span></span>

<span data-ttu-id="dc28c-124">Den enhetliga $U $.</span><span class="sxs-lookup"><span data-stu-id="dc28c-124">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="dc28c-125">Referenser</span><span class="sxs-lookup"><span data-stu-id="dc28c-125">References</span></span>

- <span data-ttu-id="dc28c-126">Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="dc28c-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>