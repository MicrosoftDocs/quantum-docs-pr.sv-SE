---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: Funktionen AmplitudeAmplificationFromPartialReflections
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: 8fa6db7d5616f8c561191e3da00a69b05041b279
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191694"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="2a0d5-102">Funktionen AmplitudeAmplificationFromPartialReflections</span><span class="sxs-lookup"><span data-stu-id="2a0d5-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="2a0d5-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2a0d5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2a0d5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a0d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a0d5-105">Amplitud förstärkning med partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="2a0d5-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2a0d5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2a0d5-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="2a0d5-107">faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="2a0d5-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="2a0d5-108">Faser av partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="2a0d5-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="2a0d5-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="2a0d5-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="2a0d5-110">Reflektions operator om start tillstånd</span><span class="sxs-lookup"><span data-stu-id="2a0d5-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="2a0d5-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="2a0d5-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="2a0d5-112">Reflektions operator om mål status</span><span class="sxs-lookup"><span data-stu-id="2a0d5-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="2a0d5-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="2a0d5-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2a0d5-114">En åtgärd som implementerar amplitud-förstärkning med partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="2a0d5-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a0d5-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2a0d5-115">Remarks</span></span>

<span data-ttu-id="2a0d5-116">Amplitud förstärkning är ett specialfall av Oblivious amplitud-förstärkning där det inte finns någon system qubits och Oblivious Oracle är inställt på identitet.</span><span class="sxs-lookup"><span data-stu-id="2a0d5-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="2a0d5-117">I de flesta fall `startQubits` initieras i tillstånd $ \ket{\text{start}} \_ $1, som är $-$1-eigenstate `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="2a0d5-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>