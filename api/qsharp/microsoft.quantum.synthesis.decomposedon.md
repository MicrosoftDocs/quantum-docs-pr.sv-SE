---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Funktionen DecomposedOn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855518"
---
# <a name="decomposedon-function"></a><span data-ttu-id="2d24b-102">Funktionen DecomposedOn</span><span class="sxs-lookup"><span data-stu-id="2d24b-102">DecomposedOn function</span></span>

<span data-ttu-id="2d24b-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2d24b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2d24b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d24b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d24b-105">Deskapar en permutation för en variabel</span><span class="sxs-lookup"><span data-stu-id="2d24b-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="2d24b-106">Description</span><span class="sxs-lookup"><span data-stu-id="2d24b-106">Description</span></span>

<span data-ttu-id="2d24b-107">Gett en permutation $ \pi $ ( `perm` ) och ett index $i $ ( `index` ), den här metoden returnerar tre permutationer $ ((\ pi_l, \ pi_r), \pi ') $ så att avbildningarna av $ \ pi_l $ och $ \ pi_r $ inte ändrar bitar i deras element i andra index än $i $ och bilder av $ \pi $ ändra inte bit $i $ i sina element.</span><span class="sxs-lookup"><span data-stu-id="2d24b-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="2d24b-108">Indata</span><span class="sxs-lookup"><span data-stu-id="2d24b-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="2d24b-109">behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2d24b-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="2d24b-110">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d24b-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="2d24b-111">Utdata: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="2d24b-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="2d24b-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="2d24b-112">Example</span></span>

<span data-ttu-id="2d24b-113">Anta att indata är perm = [0, 2, 3, 5, 7, 1, 4, 6] och index = 0, beräknar den här funktionen tre permutationer baserat på följande tabell, som visar permutationen `perm` i binär notation med element i grupp A och bilder i grupp D.  Kolumnerna listar bit indexen.</span><span class="sxs-lookup"><span data-stu-id="2d24b-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="2d24b-114">|   En |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="2d24b-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="2d24b-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-115">2 1 0</span></span> | <span data-ttu-id="2d24b-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-116">2 1 0</span></span> | <span data-ttu-id="2d24b-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-117">2 1 0</span></span> | <span data-ttu-id="2d24b-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="2d24b-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-119">0 0 0</span></span> |       |       | <span data-ttu-id="2d24b-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-120">0 0 0</span></span> | <span data-ttu-id="2d24b-121">0</span><span class="sxs-lookup"><span data-stu-id="2d24b-121">0</span></span>
| <span data-ttu-id="2d24b-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-122">0 0 1</span></span> |       |       | <span data-ttu-id="2d24b-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-123">0 1 0</span></span> | <span data-ttu-id="2d24b-124">2</span><span class="sxs-lookup"><span data-stu-id="2d24b-124">2</span></span>
| <span data-ttu-id="2d24b-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-125">0 1 0</span></span> |       |       | <span data-ttu-id="2d24b-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-126">0 1 1</span></span> | <span data-ttu-id="2d24b-127">3</span><span class="sxs-lookup"><span data-stu-id="2d24b-127">3</span></span>
| <span data-ttu-id="2d24b-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-128">0 1 1</span></span> |       |       | <span data-ttu-id="2d24b-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-129">1 0 1</span></span> | <span data-ttu-id="2d24b-130">5</span><span class="sxs-lookup"><span data-stu-id="2d24b-130">5</span></span>
| <span data-ttu-id="2d24b-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-131">1 0 0</span></span> |       |       | <span data-ttu-id="2d24b-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-132">1 1 1</span></span> | <span data-ttu-id="2d24b-133">7</span><span class="sxs-lookup"><span data-stu-id="2d24b-133">7</span></span>
| <span data-ttu-id="2d24b-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-134">1 0 1</span></span> |       |       | <span data-ttu-id="2d24b-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-135">0 0 1</span></span> | <span data-ttu-id="2d24b-136">1</span><span class="sxs-lookup"><span data-stu-id="2d24b-136">1</span></span>
| <span data-ttu-id="2d24b-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-137">1 1 0</span></span> |       |       | <span data-ttu-id="2d24b-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-138">1 0 0</span></span> | <span data-ttu-id="2d24b-139">4</span><span class="sxs-lookup"><span data-stu-id="2d24b-139">4</span></span>
| <span data-ttu-id="2d24b-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-140">1 1 1</span></span> |       |       | <span data-ttu-id="2d24b-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-141">1 1 0</span></span> | <span data-ttu-id="2d24b-142">6</span><span class="sxs-lookup"><span data-stu-id="2d24b-142">6</span></span>

<span data-ttu-id="2d24b-143">Alla värden för index som inte är lika med 0 (= index) kopieras från A till B och från D till C.</span><span class="sxs-lookup"><span data-stu-id="2d24b-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="2d24b-144">|   En |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="2d24b-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="2d24b-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-145">2 1 0</span></span> | <span data-ttu-id="2d24b-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-146">2 1 0</span></span> | <span data-ttu-id="2d24b-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-147">2 1 0</span></span> | <span data-ttu-id="2d24b-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="2d24b-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-149">0 0 0</span></span> | <span data-ttu-id="2d24b-150">0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-150">0 0</span></span>   | <span data-ttu-id="2d24b-151">0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-151">0 0</span></span>   | <span data-ttu-id="2d24b-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-152">0 0 0</span></span> |
| <span data-ttu-id="2d24b-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-153">0 0 1</span></span> | <span data-ttu-id="2d24b-154">0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-154">0 0</span></span>   | <span data-ttu-id="2d24b-155">0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-155">0 1</span></span>   | <span data-ttu-id="2d24b-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-156">0 1 0</span></span> |
| <span data-ttu-id="2d24b-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-157">0 1 0</span></span> | <span data-ttu-id="2d24b-158">0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-158">0 1</span></span>   | <span data-ttu-id="2d24b-159">0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-159">0 1</span></span>   | <span data-ttu-id="2d24b-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-160">0 1 1</span></span> |
| <span data-ttu-id="2d24b-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-161">0 1 1</span></span> | <span data-ttu-id="2d24b-162">0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-162">0 1</span></span>   | <span data-ttu-id="2d24b-163">1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-163">1 0</span></span>   | <span data-ttu-id="2d24b-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-164">1 0 1</span></span> |
| <span data-ttu-id="2d24b-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-165">1 0 0</span></span> | <span data-ttu-id="2d24b-166">1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-166">1 0</span></span>   | <span data-ttu-id="2d24b-167">1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-167">1 1</span></span>   | <span data-ttu-id="2d24b-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-168">1 1 1</span></span> |
| <span data-ttu-id="2d24b-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-169">1 0 1</span></span> | <span data-ttu-id="2d24b-170">1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-170">1 0</span></span>   | <span data-ttu-id="2d24b-171">0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-171">0 0</span></span>   | <span data-ttu-id="2d24b-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-172">0 0 1</span></span> |
| <span data-ttu-id="2d24b-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-173">1 1 0</span></span> | <span data-ttu-id="2d24b-174">1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-174">1 1</span></span>   | <span data-ttu-id="2d24b-175">1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-175">1 0</span></span>   | <span data-ttu-id="2d24b-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-176">1 0 0</span></span> |
| <span data-ttu-id="2d24b-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-177">1 1 1</span></span> | <span data-ttu-id="2d24b-178">1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-178">1 1</span></span>   | <span data-ttu-id="2d24b-179">1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-179">1 1</span></span>   | <span data-ttu-id="2d24b-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-180">1 1 0</span></span> |

<span data-ttu-id="2d24b-181">Nästa 0 placeras för det första elementet med ett tomt index i kolumn 0 i Block B och därefter placeras en 1 i B där prefixet matchar (i det första fallet den andra raden med index 0 0).</span><span class="sxs-lookup"><span data-stu-id="2d24b-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="2d24b-182">Efteråt läggs en 1 till i samma rad i block C, och sedan 0 för motsvarande prefix i block C.  Den här processen upprepas tills alla index har placerats i kolumn 0 i Block B och C.</span><span class="sxs-lookup"><span data-stu-id="2d24b-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="2d24b-183">|   En |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="2d24b-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="2d24b-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-184">2 1 0</span></span> | <span data-ttu-id="2d24b-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-185">2 1 0</span></span> | <span data-ttu-id="2d24b-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-186">2 1 0</span></span> | <span data-ttu-id="2d24b-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="2d24b-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-188">0 0 0</span></span> | <span data-ttu-id="2d24b-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-189">0 0 0</span></span> | <span data-ttu-id="2d24b-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-190">0 0 0</span></span> | <span data-ttu-id="2d24b-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-191">0 0 0</span></span> |
| <span data-ttu-id="2d24b-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-192">0 0 1</span></span> | <span data-ttu-id="2d24b-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-193">0 0 1</span></span> | <span data-ttu-id="2d24b-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-194">0 1 1</span></span> | <span data-ttu-id="2d24b-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-195">0 1 0</span></span> |
| <span data-ttu-id="2d24b-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-196">0 1 0</span></span> | <span data-ttu-id="2d24b-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-197">0 1 0</span></span> | <span data-ttu-id="2d24b-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-198">0 1 0</span></span> | <span data-ttu-id="2d24b-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-199">0 1 1</span></span> |
| <span data-ttu-id="2d24b-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-200">0 1 1</span></span> | <span data-ttu-id="2d24b-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-201">0 1 1</span></span> | <span data-ttu-id="2d24b-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-202">1 0 1</span></span> | <span data-ttu-id="2d24b-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-203">1 0 1</span></span> |
| <span data-ttu-id="2d24b-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-204">1 0 0</span></span> | <span data-ttu-id="2d24b-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-205">1 0 0</span></span> | <span data-ttu-id="2d24b-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-206">1 1 0</span></span> | <span data-ttu-id="2d24b-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-207">1 1 1</span></span> |
| <span data-ttu-id="2d24b-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-208">1 0 1</span></span> | <span data-ttu-id="2d24b-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-209">1 0 1</span></span> | <span data-ttu-id="2d24b-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-210">0 0 1</span></span> | <span data-ttu-id="2d24b-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-211">0 0 1</span></span> |
| <span data-ttu-id="2d24b-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-212">1 1 0</span></span> | <span data-ttu-id="2d24b-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-213">1 1 0</span></span> | <span data-ttu-id="2d24b-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-214">1 0 0</span></span> | <span data-ttu-id="2d24b-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-215">1 0 0</span></span> |
| <span data-ttu-id="2d24b-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-216">1 1 1</span></span> | <span data-ttu-id="2d24b-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-217">1 1 1</span></span> | <span data-ttu-id="2d24b-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="2d24b-218">1 1 1</span></span> | <span data-ttu-id="2d24b-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="2d24b-219">1 1 0</span></span> |

<span data-ttu-id="2d24b-220">Vi kan läsa tre nya permutationer från tabellen:</span><span class="sxs-lookup"><span data-stu-id="2d24b-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="2d24b-221">$ \ pi_l $ med element i A, bilder i B (vänster)</span><span class="sxs-lookup"><span data-stu-id="2d24b-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="2d24b-222">$ \ pi_r $ med element i D, bilder i C (höger)</span><span class="sxs-lookup"><span data-stu-id="2d24b-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="2d24b-223">$ \pi $ med element i B, bilder i C (rest)</span><span class="sxs-lookup"><span data-stu-id="2d24b-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="2d24b-224">Observera att eftersom design bit värden inte ändras i $ \ pi_l $ och $ \ pi_r $ för index 1 och 2, och bit värdena inte ändras för i $ \ pi_ $ för index 0.</span><span class="sxs-lookup"><span data-stu-id="2d24b-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="2d24b-225">Observera också att $ \ pi_l $ och $ \ pi_r $ måste vara inversen.</span><span class="sxs-lookup"><span data-stu-id="2d24b-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="2d24b-226">De härledda och returnerade permutationerna är: Left = [0, 1, 2, 3, 4, 6, 7] höger = [0, 1, 3, 2, 4, 5, 7, 6] rest = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="2d24b-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>