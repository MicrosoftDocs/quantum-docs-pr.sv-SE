---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729619"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="2c7a5-102">ApplyFermionicSWAP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2c7a5-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="2c7a5-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c7a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c7a5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c7a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c7a5-105">Tillämpar Fermionic-VÄXLINGen.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="2c7a5-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2c7a5-106">Description</span></span>

<span data-ttu-id="2c7a5-107">Detta byter i princip qubits vid användning av en global fas på-1 om båda qubits är 1.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="2c7a5-108">Bevarar symmetrization av banor.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="2c7a5-109">Mer information finns i .</span><span class="sxs-lookup"><span data-stu-id="2c7a5-109">See  for more information.</span></span>

<span data-ttu-id="2c7a5-110">Den här åtgärden representeras av den enhetliga operatorn \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 & & 1 & 0 & 0 & 0 & \\ \\ 0 \\ \\ \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="2c7a5-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2c7a5-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="2c7a5-112">Indata</span><span class="sxs-lookup"><span data-stu-id="2c7a5-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="2c7a5-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2c7a5-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2c7a5-114">Den första qubit som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="2c7a5-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2c7a5-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2c7a5-116">Den andra qubit som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c7a5-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c7a5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2c7a5-118">Referenser</span><span class="sxs-lookup"><span data-stu-id="2c7a5-118">References</span></span>

- [<span data-ttu-id="2c7a5-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, Jonas McClain, Hartmut Neven, Garnet Kin-Lic-kanal* , arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="2c7a5-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="2c7a5-120">Se även</span><span class="sxs-lookup"><span data-stu-id="2c7a5-120">See Also</span></span>

- [<span data-ttu-id="2c7a5-121">Microsoft. Quantum. inbyggd. växling</span><span class="sxs-lookup"><span data-stu-id="2c7a5-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)