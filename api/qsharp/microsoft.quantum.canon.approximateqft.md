---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850328"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="71398-102">ApproximateQFT-åtgärd</span><span class="sxs-lookup"><span data-stu-id="71398-102">ApproximateQFT operation</span></span>

<span data-ttu-id="71398-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71398-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71398-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71398-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71398-105">Använd den ungefärliga AQFT-transformeringen (Quantum Fourier Transform) till ett Quantum-register.</span><span class="sxs-lookup"><span data-stu-id="71398-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="71398-106">Indata</span><span class="sxs-lookup"><span data-stu-id="71398-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="71398-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71398-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71398-108">Ungefärlig parameter som avgör på vilken nivå de kontrollerade Z-rotationer som sker i QFT-kretsen rensas.</span><span class="sxs-lookup"><span data-stu-id="71398-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="71398-109">Den ungefärliga parametern a bestämmer rensnings nivån för Z-rotationer, d.v.s. en ∈ {0.. n} och alla Z-rotationer 2π/2 000 där k>a tas bort från QFT-kretsen.</span><span class="sxs-lookup"><span data-stu-id="71398-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="71398-110">Det är känt att för k >= log ₂ (n) + log ₂ (1/ε) + 3 en kan vara kopplad | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="71398-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="71398-111">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="71398-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="71398-112">Quantum-register för n-qubits som den ungefärliga Quantum Fourier-transformeringen tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="71398-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71398-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71398-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="71398-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="71398-114">Remarks</span></span>

<span data-ttu-id="71398-115">AQFT kräver Z-rotations grindar av formatet 2π/2 000 och Hadamard Gates.</span><span class="sxs-lookup"><span data-stu-id="71398-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="71398-116">Indata och utdata antas vara kodade i big endian encoding.</span><span class="sxs-lookup"><span data-stu-id="71398-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="71398-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="71398-117">References</span></span>

- [<span data-ttu-id="71398-118">*M. Roetteler, Th. Beth*, anv. algebra eng. Commune. Compute. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="71398-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="71398-119">*D. Coppersmith* arXiv: Quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="71398-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)