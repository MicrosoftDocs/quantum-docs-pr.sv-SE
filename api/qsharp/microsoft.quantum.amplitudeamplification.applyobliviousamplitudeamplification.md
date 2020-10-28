---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732006"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="18da2-102">ApplyObliviousAmplitudeAmplification-åtgärd</span><span class="sxs-lookup"><span data-stu-id="18da2-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="18da2-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="18da2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="18da2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18da2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18da2-105">Oblivious amplitud-förstärkning genom att ange partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="18da2-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="18da2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="18da2-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="18da2-107">faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="18da2-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="18da2-108">Faser av partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="18da2-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="18da2-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="18da2-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="18da2-110">Reflektions operator om start tillstånd för hjälp register</span><span class="sxs-lookup"><span data-stu-id="18da2-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="18da2-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="18da2-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="18da2-112">Reflektions operator om mål tillstånd för hjälp registrering</span><span class="sxs-lookup"><span data-stu-id="18da2-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="18da2-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="18da2-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="18da2-114">Enhetlig Oracle-$O $ av typ `ObliviousOracle` som fungerar tillsammans i hjälp-och system registren.</span><span class="sxs-lookup"><span data-stu-id="18da2-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="18da2-115">auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="18da2-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="18da2-116">Hjälp register</span><span class="sxs-lookup"><span data-stu-id="18da2-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="18da2-117">systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="18da2-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="18da2-118">System register</span><span class="sxs-lookup"><span data-stu-id="18da2-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="18da2-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18da2-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="18da2-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="18da2-120">Remarks</span></span>

<span data-ttu-id="18da2-121">Angett ett särskilt start tillstånd $ \ket{\text{Start}} \_ a $, ett visst hjälp mål tillstånd $ \ket{\text{Target}} \_ a $ och alla system tillstånd $ \ket{\psi} \_ s $, Antag att \begin{align} O\ket {\ text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{Target} ^ \perp} \_ a\cdots \end{align} för en del $U $.</span><span class="sxs-lookup"><span data-stu-id="18da2-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="18da2-122">Med en sekvens av reflektioner om start-och mål tillstånden i det extra register som överlämnas av program `signalOracle` och dess intilliggande, kan sannolikheten för att använda U ändras.</span><span class="sxs-lookup"><span data-stu-id="18da2-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="18da2-123">I de flesta fall `auxiliaryRegister` initieras status $ \ket{\text{Start}} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="18da2-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="18da2-124">Referenser</span><span class="sxs-lookup"><span data-stu-id="18da2-124">References</span></span>

<span data-ttu-id="18da2-125">Se</span><span class="sxs-lookup"><span data-stu-id="18da2-125">See</span></span>

- <span data-ttu-id="18da2-126">[ *D.W. bär, am, barn, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) för standard versionen.</span><span class="sxs-lookup"><span data-stu-id="18da2-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="18da2-127">Se</span><span class="sxs-lookup"><span data-stu-id="18da2-127">See</span></span>
- <span data-ttu-id="18da2-128">[ *G.H. låg, I.L. Chuang*](https://arxiv.org/abs/1610.06546) för en generalisering till partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="18da2-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>