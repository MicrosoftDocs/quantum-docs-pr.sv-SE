---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Funktionen StandardAmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843932"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="cef08-102">Funktionen StandardAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="cef08-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="cef08-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="cef08-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="cef08-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cef08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cef08-105">Standardalgoritm för Amplituds förstärkning</span><span class="sxs-lookup"><span data-stu-id="cef08-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="cef08-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cef08-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="cef08-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cef08-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cef08-108">Antal iterationer $n $ för amplitud förstärkning</span><span class="sxs-lookup"><span data-stu-id="cef08-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="cef08-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="cef08-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="cef08-110">Enhetlig Oracle $A $ som förbereder start tillstånd</span><span class="sxs-lookup"><span data-stu-id="cef08-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="cef08-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cef08-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cef08-112">Index för att flagga qubit</span><span class="sxs-lookup"><span data-stu-id="cef08-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="cef08-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="cef08-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="cef08-114">En åtgärd som implementerar en Quantum-algoritm för standard amplituds förstärkning</span><span class="sxs-lookup"><span data-stu-id="cef08-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="cef08-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cef08-115">Remarks</span></span>

<span data-ttu-id="cef08-116">Det här är standardalgoritmen för amplituds förstärkning som erhålls genom ett val av reflektions faser som beräknas genom `AmpAmpPhasesStandard` att \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} den här åtgärden förbereder status \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket {1} \_ f\ket {\ text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} i de flesta fall, `flagQubit` och `auxiliaryRegister` initieras i tillstånd $ \ket {0} \_ f\ket {0} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="cef08-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="cef08-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="cef08-117">References</span></span>

- [<span data-ttu-id="cef08-118">*G. Brassard, P. Hoyer, M. Mosca, A. tapp*</span><span class="sxs-lookup"><span data-stu-id="cef08-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)