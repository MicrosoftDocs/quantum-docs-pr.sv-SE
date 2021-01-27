---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830081"
---
# <a name="assertphase-operation"></a><span data-ttu-id="f3b08-102">AssertPhase-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f3b08-102">AssertPhase operation</span></span>

<span data-ttu-id="f3b08-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f3b08-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f3b08-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3b08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3b08-105">Förutsätter att fasen för ett Equal-positions läge har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="f3b08-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="f3b08-106">Description</span><span class="sxs-lookup"><span data-stu-id="f3b08-106">Description</span></span>

<span data-ttu-id="f3b08-107">Den här åtgärden förutsätter att fasen $ \phi $ i ett Quantum-tillstånd som kan uttryckas som $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1} ) $ för vissa valfria verkliga $t $ har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="f3b08-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="f3b08-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f3b08-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="f3b08-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3b08-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f3b08-110">Det förväntade värdet för $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="f3b08-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="f3b08-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f3b08-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f3b08-112">Qubit som lagrar det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="f3b08-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="f3b08-113">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3b08-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f3b08-114">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="f3b08-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3b08-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3b08-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f3b08-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="f3b08-116">Example</span></span>

<span data-ttu-id="f3b08-117">Följande kontroll lyckas: `qubit` är i läget $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ ket {0} + e ^ {i 0,5} \ sqrt {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="f3b08-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="f3b08-118">`qubit` är i tillstånd $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ ket {0} + e ^ {-i 0,5} \ sqrt {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="f3b08-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="f3b08-119">`qubit` är i tillstånd $ \ket{\psi} = e ^ {-i 2,2} \ sqrt {1/2} \ ket {0} + e ^ {i 0,2} \ sqrt {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="f3b08-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`