---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727321"
---
# <a name="assertphase-operation"></a><span data-ttu-id="27def-102">AssertPhase-åtgärd</span><span class="sxs-lookup"><span data-stu-id="27def-102">AssertPhase operation</span></span>

<span data-ttu-id="27def-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="27def-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="27def-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27def-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27def-105">Förutsätter att fasen för ett Equal-positions läge har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="27def-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="27def-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="27def-106">Description</span></span>

<span data-ttu-id="27def-107">Den här åtgärden förutsätter att fasen $ \phi $ i ett Quantum-tillstånd som kan uttryckas som $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1} ) $ för vissa valfria verkliga $t $ har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="27def-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="27def-108">Indata</span><span class="sxs-lookup"><span data-stu-id="27def-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="27def-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27def-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27def-110">Det förväntade värdet för $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="27def-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="27def-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27def-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27def-112">Qubit som lagrar det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="27def-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="27def-113">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27def-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27def-114">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="27def-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27def-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27def-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

