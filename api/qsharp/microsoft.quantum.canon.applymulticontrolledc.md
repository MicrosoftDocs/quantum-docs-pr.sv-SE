---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 36010ba667190c237b64f60b7246010199a8ba1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729472"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="3da52-102">ApplyMultiControlledC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3da52-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="3da52-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3da52-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3da52-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3da52-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3da52-105">Använder en multiplicerad, kontrollerad version av en åtgärd med enkel kontroll.</span><span class="sxs-lookup"><span data-stu-id="3da52-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="3da52-106">Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.</span><span class="sxs-lookup"><span data-stu-id="3da52-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3da52-107">Indata</span><span class="sxs-lookup"><span data-stu-id="3da52-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="3da52-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3da52-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3da52-109">En åtgärd som styrs av en enskild qubit.</span><span class="sxs-lookup"><span data-stu-id="3da52-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="3da52-110">Den första qubit i argumentet för åtgärden antas vara en kontroll och resten antas vara mål qubits.</span><span class="sxs-lookup"><span data-stu-id="3da52-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="3da52-111">`ApplyMultiControlled` anropar alltid `singlyControlledOp` med ett argument av längden minst 1.</span><span class="sxs-lookup"><span data-stu-id="3da52-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="3da52-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="3da52-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="3da52-113">Den kontrollerade-styrda-inte porten som ska användas för konstruktion.</span><span class="sxs-lookup"><span data-stu-id="3da52-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="3da52-114">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3da52-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3da52-115">Den qubits som ska `singlyControlledOp` kontrol leras på.</span><span class="sxs-lookup"><span data-stu-id="3da52-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="3da52-116">Längden `controls` måste vara minst 1.</span><span class="sxs-lookup"><span data-stu-id="3da52-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="3da52-117">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3da52-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3da52-118">Den mål-qubits som `singlyControlledOp` reagerar på.</span><span class="sxs-lookup"><span data-stu-id="3da52-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3da52-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3da52-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3da52-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3da52-120">Remarks</span></span>

<span data-ttu-id="3da52-121">Den här åtgärden använder bara ren Ancilla-qubits.</span><span class="sxs-lookup"><span data-stu-id="3da52-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="3da52-122">För förklaringen och krets diagrammet se bild 4,10, avsnitt 4,3 i Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="3da52-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="3da52-123">Referenser</span><span class="sxs-lookup"><span data-stu-id="3da52-123">References</span></span>

- [<span data-ttu-id="3da52-124">*Michael A. Nielsen, Isak L. Chuang* , Quantum-beräkning och Quantum-information</span><span class="sxs-lookup"><span data-stu-id="3da52-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="3da52-125">Se även</span><span class="sxs-lookup"><span data-stu-id="3da52-125">See Also</span></span>

- [<span data-ttu-id="3da52-126">Microsoft. Quantum. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="3da52-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)