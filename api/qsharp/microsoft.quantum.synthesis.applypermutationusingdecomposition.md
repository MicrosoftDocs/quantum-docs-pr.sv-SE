---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 5b25ef3327bbca2dfdbe8fa876f3f797dddf77e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192136"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="cdc75-102">ApplyPermutationUsingDecomposition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="cdc75-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="cdc75-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cdc75-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cdc75-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdc75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cdc75-105">Permutes amplituderna i ett Quantum-tillstånd med en permutation med hjälp av nedbrytnings syntes.</span><span class="sxs-lookup"><span data-stu-id="cdc75-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cdc75-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cdc75-106">Description</span></span>

<span data-ttu-id="cdc75-107">I den här proceduren implementeras sammanfattnings metoden för nedbrytning.</span><span class="sxs-lookup"><span data-stu-id="cdc75-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="cdc75-108">Indatamängden är en permutation $ \pi $ över $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, som representerar en $n $-variabel omvänd boolesk funktion.</span><span class="sxs-lookup"><span data-stu-id="cdc75-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="cdc75-109">Algoritmen utför upprepat följande steg för varje variabel index $i $:</span><span class="sxs-lookup"><span data-stu-id="cdc75-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="cdc75-110">Compute $ ((\ pi_l, \ pi_r), \pi ') $ så att avbildningarna av $ \ pi_l $ och $ \ pi_r $ inte ändrar bitar i deras element i andra index än $i $ och bilder av $ \pi $ ändra inte bit $i $ i sina element.</span><span class="sxs-lookup"><span data-stu-id="cdc75-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="cdc75-111">Ställ in $ \pi \leftarrow \pi $ och Härled sanningen-tabeller från $ \ pi_l $ och $ \ pi_r $ baserat på element som inte är fasta punkter.</span><span class="sxs-lookup"><span data-stu-id="cdc75-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="cdc75-112">När du har tillämpat de här stegen för alla variabel index, blir den återstående permutationen $ \pi $ identiteten, och baserat på de insamlade sanningen-tabellerna och indexen, kan en använda sanningen-tabellens kontrollerade @"microsoft.quantum.intrinsic.x" åtgärder med hjälp av @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" åtgärden.</span><span class="sxs-lookup"><span data-stu-id="cdc75-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="cdc75-113">Variabeln order är $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="cdc75-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="cdc75-114">En anpassad variabel ordning kan anges i åtgärden @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="cdc75-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="cdc75-115">Indata</span><span class="sxs-lookup"><span data-stu-id="cdc75-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="cdc75-116">behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cdc75-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cdc75-117">En permutation av $2 ^ n $ elementen börjar från 0.</span><span class="sxs-lookup"><span data-stu-id="cdc75-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="cdc75-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cdc75-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cdc75-119">En lista med $n $ qubits som permutationen tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="cdc75-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdc75-120">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdc75-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="cdc75-121">Referenser</span><span class="sxs-lookup"><span data-stu-id="cdc75-121">References</span></span>

- [<span data-ttu-id="cdc75-122">*Alexis de Vos*, *Yvan van Rentergem*, adv. i matematik. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="cdc75-122">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="cdc75-123">*Mathias Soeken*, *Lisa Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of symbolisk beräkning 73 (2016), sid. 1--26</span><span class="sxs-lookup"><span data-stu-id="cdc75-123">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="cdc75-124">Se även</span><span class="sxs-lookup"><span data-stu-id="cdc75-124">See Also</span></span>

- [<span data-ttu-id="cdc75-125">Microsoft. Quantum. syntes. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="cdc75-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="cdc75-126">Microsoft. Quantum. syntes. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="cdc75-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)