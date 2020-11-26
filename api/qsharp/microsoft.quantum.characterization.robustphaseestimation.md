---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216089"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="d1d48-102">RobustPhaseEstimation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d1d48-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="d1d48-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d1d48-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d1d48-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1d48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1d48-105">Utför den robusta uppskattnings algoritmen för en icke-iterativ Quantum-fas för en viss Oracle `U` -och eigenstate och ger en enda verklig uppskattning av fasen med avvikelse skalning vid Heisenberg-gränsen.</span><span class="sxs-lookup"><span data-stu-id="d1d48-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="d1d48-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d1d48-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="d1d48-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1d48-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1d48-108">Detta ger en uppskattning av $ \phi $ med standard avvikelsen $ \sigma \le 2 \ Pi/2 ^ \text{bitsPrecision} $ med ett antal frågor som kan skalas, t. ex. $ \sigma \le 10,7 \pi/\text{antal frågor} $.</span><span class="sxs-lookup"><span data-stu-id="d1d48-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="d1d48-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="d1d48-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="d1d48-110">En åtgärd som implementerar $U ^ m $ för angivet heltals-potenser $m $.</span><span class="sxs-lookup"><span data-stu-id="d1d48-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="d1d48-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d1d48-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d1d48-112">Ett Quantum-register som $U $ reagerar på.</span><span class="sxs-lookup"><span data-stu-id="d1d48-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="d1d48-113">Om den lagrar en eigenstate $ \ket{\phi} $ $U $ $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ för $ \phi\in (-\pi, \pi] $ en okänd fas.</span><span class="sxs-lookup"><span data-stu-id="d1d48-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="d1d48-114">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d1d48-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="d1d48-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d1d48-115">Remarks</span></span>

<span data-ttu-id="d1d48-116">I gränsen för ett stort antal frågor Cramer-Rao nedre gränser för standard avvikelsen för uppskattningen av $ \phi $ som uppfyller $ \sigma \ge 2 \pi/\text{antal frågor} $.</span><span class="sxs-lookup"><span data-stu-id="d1d48-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="d1d48-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="d1d48-117">References</span></span>

- <span data-ttu-id="d1d48-118">Robust kalibrering av en universell Single-Qubit Gate-Set via robust fas uppskattning Shelby Kimmel, Guang lämnar demon Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="d1d48-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>