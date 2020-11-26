---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202268"
---
# <a name="assertphase-operation"></a><span data-ttu-id="67ea0-102">AssertPhase-åtgärd</span><span class="sxs-lookup"><span data-stu-id="67ea0-102">AssertPhase operation</span></span>

<span data-ttu-id="67ea0-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="67ea0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="67ea0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67ea0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67ea0-105">Förutsätter att fasen för ett Equal-positions läge har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="67ea0-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="67ea0-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="67ea0-106">Description</span></span>

<span data-ttu-id="67ea0-107">Den här åtgärden förutsätter att fasen $ \phi $ i ett Quantum-tillstånd som kan uttryckas som $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1} ) $ för vissa valfria verkliga $t $ har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="67ea0-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="67ea0-108">Indata</span><span class="sxs-lookup"><span data-stu-id="67ea0-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="67ea0-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67ea0-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67ea0-110">Det förväntade värdet för $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="67ea0-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="67ea0-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="67ea0-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="67ea0-112">Qubit som lagrar det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="67ea0-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="67ea0-113">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67ea0-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67ea0-114">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="67ea0-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67ea0-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67ea0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

