---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729469"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="a2d82-102">ApplyMultiControlledCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a2d82-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="a2d82-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2d82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2d82-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2d82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2d82-105">Använder en multiplicerad, kontrollerad version av en åtgärd med enkel kontroll.</span><span class="sxs-lookup"><span data-stu-id="a2d82-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="a2d82-106">Modifieraren `CA` anger att en enskild-qubit-åtgärd är kontrollerbar och adjointable.</span><span class="sxs-lookup"><span data-stu-id="a2d82-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a2d82-107">Indata</span><span class="sxs-lookup"><span data-stu-id="a2d82-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="a2d82-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="a2d82-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a2d82-109">En åtgärd som styrs av en enskild qubit.</span><span class="sxs-lookup"><span data-stu-id="a2d82-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="a2d82-110">Den första qubit i argumentet för åtgärden förutsätter vara en kontroll och resten antas vara mål qubits.</span><span class="sxs-lookup"><span data-stu-id="a2d82-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="a2d82-111">`ApplyMultiControlled` anropar alltid `singlyControlledOp` med ett argument av längden minst 1.</span><span class="sxs-lookup"><span data-stu-id="a2d82-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="a2d82-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="a2d82-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="a2d82-113">Den kontrollerade-styrda-inte porten som ska användas för konstruktion.</span><span class="sxs-lookup"><span data-stu-id="a2d82-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="a2d82-114">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2d82-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a2d82-115">Den qubits som ska `singlyControlledOp` kontrol leras på.</span><span class="sxs-lookup"><span data-stu-id="a2d82-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="a2d82-116">Längden `controls` måste vara minst 1.</span><span class="sxs-lookup"><span data-stu-id="a2d82-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="a2d82-117">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2d82-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a2d82-118">Den mål-qubits som `singlyControlledOp` reagerar på.</span><span class="sxs-lookup"><span data-stu-id="a2d82-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2d82-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2d82-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a2d82-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a2d82-120">Remarks</span></span>

<span data-ttu-id="a2d82-121">Den här åtgärden använder bara ren Ancilla-qubits.</span><span class="sxs-lookup"><span data-stu-id="a2d82-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="a2d82-122">För förklaringen och krets diagrammet se bild 4,10, avsnitt 4,3 i Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="a2d82-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="a2d82-123">Referenser</span><span class="sxs-lookup"><span data-stu-id="a2d82-123">References</span></span>

- [<span data-ttu-id="a2d82-124">*Michael A. Nielsen, Isak L. Chuang* , Quantum-beräkning och Quantum-information</span><span class="sxs-lookup"><span data-stu-id="a2d82-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="a2d82-125">Se även</span><span class="sxs-lookup"><span data-stu-id="a2d82-125">See Also</span></span>

- [<span data-ttu-id="a2d82-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="a2d82-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)