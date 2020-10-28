---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726433"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="7aef6-102">RandomWalkPhaseEstimation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7aef6-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="7aef6-103">Namnrymd: [Microsoft. Quantum. Research. karakterisering](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7aef6-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="7aef6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7aef6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7aef6-105">Utför iterativ fas uppskattning med en slumpmässig genom gång för att approximera Bayesian-härledningen på de klassiska mått resultaten från en specifik Oracle och eigenstate.</span><span class="sxs-lookup"><span data-stu-id="7aef6-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="7aef6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7aef6-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="7aef6-107">initialMean: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7aef6-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7aef6-108">Medelvärde för den första normala tidigare distributionen över $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="7aef6-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="7aef6-109">initialStdDev: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7aef6-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7aef6-110">Standard avvikelse för den initiala normal tidigare distributionen över $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="7aef6-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="7aef6-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7aef6-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7aef6-112">Antalet mätningar som ska godkännas i den slutliga beräkningen i efterhand.</span><span class="sxs-lookup"><span data-stu-id="7aef6-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="7aef6-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7aef6-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7aef6-114">Det totala antalet mätningar som kan vidtas innan åtgärden anses ha misslyckats.</span><span class="sxs-lookup"><span data-stu-id="7aef6-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="7aef6-115">avspolning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7aef6-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7aef6-116">Antal resultat som ska glömmas när konsekvens kontroller misslyckats.</span><span class="sxs-lookup"><span data-stu-id="7aef6-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="7aef6-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="7aef6-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="7aef6-118">En åtgärd som representerar en enhetlig $U $ t. ex. $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ för eigenstates $ \ket{\phi} $ med okänd fas $ \phi \in \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="7aef6-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="7aef6-119">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7aef6-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7aef6-120">Ett register som $U $ handlar om.</span><span class="sxs-lookup"><span data-stu-id="7aef6-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="7aef6-121">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7aef6-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7aef6-122">Den slutliga uppskattningen $ \hat{\phi} \mathrel{: =} \expect [\phi] $, där förväntat sker över alla accepterade data.</span><span class="sxs-lookup"><span data-stu-id="7aef6-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="7aef6-123">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7aef6-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="7aef6-124">Uppskattning av iterativa faser och Eigenstates</span><span class="sxs-lookup"><span data-stu-id="7aef6-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="7aef6-125">I allmänhet behöver ingångs registreringen `eigenstate` inte vara en eigenstate $ \ket{\phi} $ $U $, men kan vara en överposition över eigenstates.</span><span class="sxs-lookup"><span data-stu-id="7aef6-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="7aef6-126">Anta att indatamängden anges av \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align} där $ \{ \alpha \_ j \} $ är komplexa koefficienter som $ \sum \_ j | \alpha \_ j | ^ 2 = $1 och där $U \ket{\phi \_ j} = \phi \_ j\ket {\ Fi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="7aef6-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="7aef6-127">Sedan konvergerar periodiska fas uppskattningar till en enda eigenstate enligt beskrivningen i [utvecklings guiden](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="7aef6-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="7aef6-128">Experiment design</span><span class="sxs-lookup"><span data-stu-id="7aef6-128">Experiment Design</span></span>

<span data-ttu-id="7aef6-129">Mätnings tiderna $t $ och inversions vinklarna $ \theta $ som `oracle` väljs enligt *partikel gissans heuristik* , \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.</span><span class="sxs-lookup"><span data-stu-id="7aef6-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic* , \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="7aef6-130">\end{align} den här heuristiken är optimal för att minska den förväntade föregående avvikelsen i upprepnings fas uppskattningen under antagandet av en normal tidigare period.</span><span class="sxs-lookup"><span data-stu-id="7aef6-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="7aef6-131">Optimalhet</span><span class="sxs-lookup"><span data-stu-id="7aef6-131">Optimality</span></span>

<span data-ttu-id="7aef6-132">Den här åtgärden uppskattar den optimala uppskattningen för fasen $ \phi $, som utvärderas med hjälp av kvadratisk förlust $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="7aef6-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="7aef6-133">Se [uppskattning av Bayesian-fasen](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) för mer information om statistik för uppskattning av iterativa faser.</span><span class="sxs-lookup"><span data-stu-id="7aef6-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="7aef6-134">Referenser</span><span class="sxs-lookup"><span data-stu-id="7aef6-134">References</span></span>

- <span data-ttu-id="7aef6-135">Uppskjuten *et al.* 2011 [Doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="7aef6-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="7aef6-136">Wiebe *et al.* 2013 [Doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="7aef6-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="7aef6-137">Wiebe och granade 2018 *(i förberedelse)* .</span><span class="sxs-lookup"><span data-stu-id="7aef6-137">Wiebe and Granade 2018 *(in preparation)* .</span></span>