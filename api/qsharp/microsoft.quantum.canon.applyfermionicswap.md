---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218809"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="ae17b-102">ApplyFermionicSWAP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ae17b-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="ae17b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae17b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae17b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae17b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae17b-105">Tillämpar Fermionic-VÄXLINGen.</span><span class="sxs-lookup"><span data-stu-id="ae17b-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ae17b-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ae17b-106">Description</span></span>

<span data-ttu-id="ae17b-107">Detta byter i princip qubits vid användning av en global fas på-1 om båda qubits är 1.</span><span class="sxs-lookup"><span data-stu-id="ae17b-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="ae17b-108">Bevarar symmetrization av banor.</span><span class="sxs-lookup"><span data-stu-id="ae17b-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="ae17b-109">Mer information finns i .</span><span class="sxs-lookup"><span data-stu-id="ae17b-109">See  for more information.</span></span>

<span data-ttu-id="ae17b-110">Den här åtgärden representeras av den enhetliga operatorn \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 & & 1 & 0 & 0 & 0 & \\ \\ 0 \\ \\ \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="ae17b-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="ae17b-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ae17b-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="ae17b-112">Indata</span><span class="sxs-lookup"><span data-stu-id="ae17b-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="ae17b-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae17b-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae17b-114">Den första qubit som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="ae17b-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="ae17b-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae17b-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae17b-116">Den andra qubit som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="ae17b-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae17b-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae17b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="ae17b-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="ae17b-118">References</span></span>

- [<span data-ttu-id="ae17b-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, Jonas McClain, Hartmut Neven, Garnet Kin-Lic-kanal*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="ae17b-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="ae17b-120">Se även</span><span class="sxs-lookup"><span data-stu-id="ae17b-120">See Also</span></span>

- [<span data-ttu-id="ae17b-121">Microsoft. Quantum. inbyggd. växling</span><span class="sxs-lookup"><span data-stu-id="ae17b-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)