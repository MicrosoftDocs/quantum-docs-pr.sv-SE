---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 092a350e42d8d90942de13530fefd761b5187e1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729478"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="7d5e0-102">ApplyLowDepthAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7d5e0-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="7d5e0-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d5e0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7d5e0-105">Inverterar en specifik mål-qubit, om och bara om båda kontroll qubits är i läget 1, med T-djup 1, med hjälp av mått för att utföra den angränsande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="7d5e0-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7d5e0-106">Description</span></span>

<span data-ttu-id="7d5e0-107">Inverterar `target` om och endast om båda kontrollerna är 1, men antar att de `target` är i tillstånd 0.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="7d5e0-108">Åtgärden har T-Count 4, T-djup 1 och kräver en qubit och kan därför föredras för en CCNOT-åtgärd, om `target` är känt som 0.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="7d5e0-109">Det angränsande av den här åtgärden är mått baserat och kräver inga T-grindar och ingen hjälps qubit.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="7d5e0-110">Indata</span><span class="sxs-lookup"><span data-stu-id="7d5e0-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="7d5e0-111">control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d5e0-112">Första kontrollen qubit</span><span class="sxs-lookup"><span data-stu-id="7d5e0-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="7d5e0-113">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d5e0-114">Qubit för andra kontrollen</span><span class="sxs-lookup"><span data-stu-id="7d5e0-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7d5e0-115">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d5e0-116">Mål tilläggs qubit; måste vara i tillstånd 0</span><span class="sxs-lookup"><span data-stu-id="7d5e0-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d5e0-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="7d5e0-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="7d5e0-118">References</span></span>

- <span data-ttu-id="7d5e0-119">Cody Jones: "nya byggen för den feltoleranta Toffoli-porten", inventering. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="7d5e0-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="7d5e0-120">Peter selinger: "Quantum-kretsar om T-djupgående One", inventering. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) Doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="7d5e0-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>