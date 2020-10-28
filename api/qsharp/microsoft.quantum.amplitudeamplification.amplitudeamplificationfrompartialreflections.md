---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: Funktionen AmplitudeAmplificationFromPartialReflections
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732046"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="a9d7a-102">Funktionen AmplitudeAmplificationFromPartialReflections</span><span class="sxs-lookup"><span data-stu-id="a9d7a-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="a9d7a-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a9d7a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a9d7a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9d7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9d7a-105">Amplitud förstärkning med partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="a9d7a-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a9d7a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a9d7a-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="a9d7a-107">faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="a9d7a-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="a9d7a-108">Faser av partiella reflektioner</span><span class="sxs-lookup"><span data-stu-id="a9d7a-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="a9d7a-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a9d7a-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a9d7a-110">Reflektions operator om start tillstånd</span><span class="sxs-lookup"><span data-stu-id="a9d7a-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="a9d7a-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a9d7a-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a9d7a-112">Reflektions operator om mål status</span><span class="sxs-lookup"><span data-stu-id="a9d7a-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="a9d7a-113">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="a9d7a-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a9d7a-114">En åtgärd som implementerar amplitud-förstärkning med partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="a9d7a-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9d7a-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a9d7a-115">Remarks</span></span>

<span data-ttu-id="a9d7a-116">Amplitud förstärkning är ett specialfall av Oblivious amplitud-förstärkning där det inte finns någon system qubits och Oblivious Oracle är inställt på identitet.</span><span class="sxs-lookup"><span data-stu-id="a9d7a-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="a9d7a-117">I de flesta fall `startQubits` initieras i tillstånd $ \ket{\text{start}} \_ $1, som är $-$1-eigenstate `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="a9d7a-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>