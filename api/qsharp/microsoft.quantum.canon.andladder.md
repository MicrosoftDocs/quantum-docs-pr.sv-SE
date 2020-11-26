---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 2c6114ec8a5caabdeea8ab7e26a4877e1633671c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209731"
---
# <a name="andladder-operation"></a><span data-ttu-id="c3984-102">AndLadder-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c3984-102">AndLadder operation</span></span>

<span data-ttu-id="c3984-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3984-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3984-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3984-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3984-105">Utför en kontrollerad "och stege" i ett register över mål qubits.</span><span class="sxs-lookup"><span data-stu-id="c3984-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c3984-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c3984-106">Description</span></span>

<span data-ttu-id="c3984-107">Den här åtgärden använder en omvandling som beskrivs i följande mappning av beräknings basen, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2). \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ där $ \ket{x \_ 1, \dots, x \_ n} $ refererar till beräknings bas tillstånden för `controls` och där $ \ket{y \_ 1, \dots, y \_ {n-1}} $ refererar till beräknings bas tillstånden för `targets` .</span><span class="sxs-lookup"><span data-stu-id="c3984-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="c3984-108">Indata</span><span class="sxs-lookup"><span data-stu-id="c3984-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="c3984-109">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="c3984-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="c3984-110">CCNOT-porten som ska användas för byggnaden.</span><span class="sxs-lookup"><span data-stu-id="c3984-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="c3984-111">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3984-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c3984-112">Ett register över qubits som ska användas som kontroller för och steg-för-steg-exempel.</span><span class="sxs-lookup"><span data-stu-id="c3984-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="c3984-113">Den här åtgärden lämnar beräknings bas tillstånd för `controls` invariant.</span><span class="sxs-lookup"><span data-stu-id="c3984-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="c3984-114">Längden `controls` måste vara minst 2 och måste vara lika med en plus längden `targets` .</span><span class="sxs-lookup"><span data-stu-id="c3984-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="c3984-115">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3984-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c3984-116">Längden `targets` måste vara minst 1 och lika med längden på `controls` minus ett.</span><span class="sxs-lookup"><span data-stu-id="c3984-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3984-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3984-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c3984-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c3984-118">Remarks</span></span>

- <span data-ttu-id="c3984-119">Används som en del av <xref:microsoft.quantum.canon.applymulticontrolledc> och <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="c3984-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="c3984-120">För förklarings diagrammet och krets diagrammet ser du bild 4,10, avsnitt 4,3 i Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="c3984-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="c3984-121">Referenser</span><span class="sxs-lookup"><span data-stu-id="c3984-121">References</span></span>

- [<span data-ttu-id="c3984-122">*Michael A. Nielsen, Isak L. Chuang*, Quantum-beräkning och Quantum-information</span><span class="sxs-lookup"><span data-stu-id="c3984-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)