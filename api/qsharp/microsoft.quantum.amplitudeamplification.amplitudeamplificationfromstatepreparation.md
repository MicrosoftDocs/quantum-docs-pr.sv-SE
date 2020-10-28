---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: Funktionen AmplitudeAmplificationFromStatePreparation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732043"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="d1b5b-102">Funktionen AmplitudeAmplificationFromStatePreparation</span><span class="sxs-lookup"><span data-stu-id="d1b5b-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="d1b5b-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d1b5b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d1b5b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1b5b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1b5b-105">Amplitud förstärkning av Oracle för partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="d1b5b-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d1b5b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d1b5b-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d1b5b-107">faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d1b5b-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d1b5b-108">Faser av partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="d1b5b-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="d1b5b-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="d1b5b-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="d1b5b-110">Enhetlig Oracle $A $ som förbereder start tillstånd</span><span class="sxs-lookup"><span data-stu-id="d1b5b-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="d1b5b-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1b5b-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1b5b-112">Index för att flagga qubit</span><span class="sxs-lookup"><span data-stu-id="d1b5b-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="d1b5b-113">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="d1b5b-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d1b5b-114">En åtgärd som implementerar amplitud-förstärkning av Oracle som implementeras av partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="d1b5b-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1b5b-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d1b5b-115">Remarks</span></span>

<span data-ttu-id="d1b5b-116">Detta tillämpar strängare villkor i form av start-och mål tillstånd än i `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="d1b5b-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="d1b5b-117">Det förutsätts att mål tillstånd är markerat med $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="d1b5b-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="d1b5b-118">Det förutsätts att \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} i de flesta fall `flagQubit` och `auxiliaryRegister` initieras i tillstånd $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="d1b5b-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>