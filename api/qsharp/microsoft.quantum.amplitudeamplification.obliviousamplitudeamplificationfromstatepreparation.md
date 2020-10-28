---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: Funktionen ObliviousAmplitudeAmplificationFromStatePreparation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731979"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="6dd4d-102">Funktionen ObliviousAmplitudeAmplificationFromStatePreparation</span><span class="sxs-lookup"><span data-stu-id="6dd4d-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="6dd4d-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="6dd4d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="6dd4d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6dd4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6dd4d-105">Oblivious amplitud-förstärkning av Oracle för partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="6dd4d-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="6dd4d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6dd4d-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="6dd4d-107">faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="6dd4d-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="6dd4d-108">Faser av partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="6dd4d-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="6dd4d-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="6dd4d-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="6dd4d-110">Enhetlig Oracle $A $ som förbereder start tillstånd</span><span class="sxs-lookup"><span data-stu-id="6dd4d-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="6dd4d-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="6dd4d-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="6dd4d-112">Enhetlig Oracle $O $ av typ `ObliviousOracle` som fungerar tillsammans i hjälp-och system registret</span><span class="sxs-lookup"><span data-stu-id="6dd4d-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="6dd4d-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6dd4d-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6dd4d-114">Index till Single-qubit flagga-register</span><span class="sxs-lookup"><span data-stu-id="6dd4d-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="6dd4d-115">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="6dd4d-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6dd4d-116">En åtgärd som implementerar Oblivious amplitud-förstärkning baserat på partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="6dd4d-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="6dd4d-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6dd4d-117">Remarks</span></span>

<span data-ttu-id="6dd4d-118">Detta tillämpar strängare villkor på form av hjälp start-och mål tillstånd än i `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="6dd4d-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="6dd4d-119">Det antas att $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ förbereder start tillstånd $ \ket{\text{Start}} \_ {FA} $ från beräknings basen $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="6dd4d-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="6dd4d-120">Det förutsätts att mål tillstånd är markerat med $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="6dd4d-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="6dd4d-121">Det antas att \begin{align} O\ket {\ text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {all}} \_ a\ket {\ text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} för en del $U $.</span><span class="sxs-lookup"><span data-stu-id="6dd4d-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>