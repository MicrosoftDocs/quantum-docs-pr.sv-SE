---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209289"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="b2dd8-102">ApplyMultiControlledCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b2dd8-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="b2dd8-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2dd8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2dd8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2dd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2dd8-105">Använder en multiplicerad, kontrollerad version av en åtgärd med enkel kontroll.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="b2dd8-106">Modifieraren `CA` anger att en enskild-qubit-åtgärd är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b2dd8-107">Indata</span><span class="sxs-lookup"><span data-stu-id="b2dd8-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="b2dd8-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="b2dd8-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b2dd8-109">En åtgärd som styrs av en enskild qubit.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="b2dd8-110">Den första qubit i argumentet för åtgärden förutsätter vara en kontroll och resten antas vara mål qubits.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="b2dd8-111">`ApplyMultiControlled` anropar alltid `singlyControlledOp` med ett argument av längden minst 1.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="b2dd8-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="b2dd8-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="b2dd8-113">Den kontrollerade-styrda-inte porten som ska användas för konstruktion.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="b2dd8-114">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2dd8-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2dd8-115">Den qubits som ska `singlyControlledOp` kontrol leras på.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="b2dd8-116">Längden `controls` måste vara minst 1.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="b2dd8-117">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2dd8-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2dd8-118">Den mål-qubits som `singlyControlledOp` reagerar på.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2dd8-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2dd8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b2dd8-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b2dd8-120">Remarks</span></span>

<span data-ttu-id="b2dd8-121">Den här åtgärden använder bara ren Ancilla-qubits.</span><span class="sxs-lookup"><span data-stu-id="b2dd8-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="b2dd8-122">För förklaringen och krets diagrammet se bild 4,10, avsnitt 4,3 i Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="b2dd8-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="b2dd8-123">Referenser</span><span class="sxs-lookup"><span data-stu-id="b2dd8-123">References</span></span>

- [<span data-ttu-id="b2dd8-124">*Michael A. Nielsen, Isak L. Chuang*, Quantum-beräkning och Quantum-information</span><span class="sxs-lookup"><span data-stu-id="b2dd8-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="b2dd8-125">Se även</span><span class="sxs-lookup"><span data-stu-id="b2dd8-125">See Also</span></span>

- [<span data-ttu-id="b2dd8-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="b2dd8-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)