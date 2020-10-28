---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729742"
---
# <a name="applyand-operation"></a><span data-ttu-id="e02fe-102">ApplyAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e02fe-102">ApplyAnd operation</span></span>

<span data-ttu-id="e02fe-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e02fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e02fe-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e02fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e02fe-105">Inverterar en specifik mål-qubit, om och bara om båda kontroll qubits är i läget 1, med hjälp av mått för att utföra den angränsande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e02fe-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="e02fe-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e02fe-106">Description</span></span>

<span data-ttu-id="e02fe-107">Inverterar `target` om och endast om båda kontrollerna är 1, men antar att de `target` är i tillstånd 0.</span><span class="sxs-lookup"><span data-stu-id="e02fe-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="e02fe-108">Åtgärden har T-Count 4, T-djup 2 och kräver ingen hjälp-qubit och kan därför vara bättre för en CCNOT-åtgärd, om `target` är känt som 0.</span><span class="sxs-lookup"><span data-stu-id="e02fe-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="e02fe-109">Det angränsande av den här åtgärden är mått baserat och kräver inga T-grindar.</span><span class="sxs-lookup"><span data-stu-id="e02fe-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="e02fe-110">Det kontrollerade programmet för den här åtgärden kräver ingen hjälps qubit, `2^c` `Rz` portar och är inte optimerat för djup, där `c` är antalet övergripande kontroll qubits, inklusive de två kontrollerna från `ApplyAnd` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e02fe-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="e02fe-111">Det intilliggande kontrollerade programmet kräver `2^c - 1` `Rz` portar (med en vinkel som är två gånger så stor som den icke-angränsande), ingen hjälps qubit och inte är optimerad för djupet.</span><span class="sxs-lookup"><span data-stu-id="e02fe-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="e02fe-112">Indata</span><span class="sxs-lookup"><span data-stu-id="e02fe-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="e02fe-113">control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e02fe-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e02fe-114">Första kontrollen qubit</span><span class="sxs-lookup"><span data-stu-id="e02fe-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="e02fe-115">control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e02fe-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e02fe-116">Qubit för andra kontrollen</span><span class="sxs-lookup"><span data-stu-id="e02fe-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e02fe-117">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e02fe-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e02fe-118">Mål tilläggs qubit; måste vara i tillstånd 0</span><span class="sxs-lookup"><span data-stu-id="e02fe-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="e02fe-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e02fe-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e02fe-120">Referenser</span><span class="sxs-lookup"><span data-stu-id="e02fe-120">References</span></span>

- <span data-ttu-id="e02fe-121">Cody Jones: "nya byggen för den feltoleranta Toffoli-porten", inventering. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="e02fe-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="e02fe-122">Craig Gidney: "hälften av kostnaden för Quantum addition", Quantum 2, sida 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) Doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="e02fe-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="e02fe-123">Mathias Soeken: "Quantum Oracle-kretsar och jul träds mönstret", [blogg artikel från 19 December 2019](https://msoeken.github.io/blog_qac.html) (Obs! förklarar den flera styrda konstruktionen)</span><span class="sxs-lookup"><span data-stu-id="e02fe-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>