---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845057"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="12a4c-102">ApplyFermionicSWAP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="12a4c-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="12a4c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="12a4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="12a4c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12a4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12a4c-105">Tillämpar Fermionic-VÄXLINGen.</span><span class="sxs-lookup"><span data-stu-id="12a4c-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="12a4c-106">Description</span><span class="sxs-lookup"><span data-stu-id="12a4c-106">Description</span></span>

<span data-ttu-id="12a4c-107">Detta byter i princip qubits vid användning av en global fas på-1 om båda qubits är 1.</span><span class="sxs-lookup"><span data-stu-id="12a4c-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="12a4c-108">Bevarar symmetrization av banor.</span><span class="sxs-lookup"><span data-stu-id="12a4c-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="12a4c-109">Mer information finns i .</span><span class="sxs-lookup"><span data-stu-id="12a4c-109">See  for more information.</span></span>

<span data-ttu-id="12a4c-110">Den här åtgärden representeras av den enhetliga operatorn \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 & & 1 & 0 & 0 & 0 & \\ \\ 0 \\ \\ \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="12a4c-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="12a4c-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="12a4c-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="12a4c-112">Indata</span><span class="sxs-lookup"><span data-stu-id="12a4c-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="12a4c-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="12a4c-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="12a4c-114">Den första qubit som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="12a4c-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="12a4c-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="12a4c-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="12a4c-116">Den andra qubit som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="12a4c-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="12a4c-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12a4c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="12a4c-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="12a4c-118">References</span></span>

- [<span data-ttu-id="12a4c-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, Jonas McClain, Hartmut Neven, Garnet Kin-Lic-kanal*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="12a4c-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="12a4c-120">Se även</span><span class="sxs-lookup"><span data-stu-id="12a4c-120">See Also</span></span>

- [<span data-ttu-id="12a4c-121">Microsoft. Quantum. inbyggd. växling</span><span class="sxs-lookup"><span data-stu-id="12a4c-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)