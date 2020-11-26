---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209323"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="33dfd-102">ApplyLowDepthAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="33dfd-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="33dfd-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33dfd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33dfd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33dfd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33dfd-105">Inverterar en specifik mål-qubit, om och bara om båda kontroll qubits är i läget 1, med T-djup 1, med hjälp av mått för att utföra den angränsande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="33dfd-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="33dfd-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33dfd-106">Description</span></span>

<span data-ttu-id="33dfd-107">Inverterar `target` om och endast om båda kontrollerna är 1, men antar att de `target` är i tillstånd 0.</span><span class="sxs-lookup"><span data-stu-id="33dfd-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="33dfd-108">Åtgärden har T-Count 4, T-djup 1 och kräver en qubit och kan därför föredras för en CCNOT-åtgärd, om `target` är känt som 0.</span><span class="sxs-lookup"><span data-stu-id="33dfd-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="33dfd-109">Det angränsande av den här åtgärden är mått baserat och kräver inga T-grindar och ingen hjälps qubit.</span><span class="sxs-lookup"><span data-stu-id="33dfd-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="33dfd-110">Indata</span><span class="sxs-lookup"><span data-stu-id="33dfd-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="33dfd-111">control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33dfd-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33dfd-112">Första kontrollen qubit</span><span class="sxs-lookup"><span data-stu-id="33dfd-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="33dfd-113">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33dfd-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33dfd-114">Qubit för andra kontrollen</span><span class="sxs-lookup"><span data-stu-id="33dfd-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="33dfd-115">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33dfd-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33dfd-116">Mål tilläggs qubit; måste vara i tillstånd 0</span><span class="sxs-lookup"><span data-stu-id="33dfd-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="33dfd-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33dfd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="33dfd-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="33dfd-118">References</span></span>

- <span data-ttu-id="33dfd-119">Cody Jones: "nya byggen för den feltoleranta Toffoli-porten", inventering. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="33dfd-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="33dfd-120">Peter selinger: "Quantum-kretsar om T-djupgående One", inventering. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) Doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="33dfd-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>