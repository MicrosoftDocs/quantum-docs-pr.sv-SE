---
<span data-ttu-id="23c6f-101">title: Beskrivning av Pauli mått: Lär dig hur du arbetar med en och flera qubit Pauli mått åtgärder.</span><span class="sxs-lookup"><span data-stu-id="23c6f-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="23c6f-102">författare: bradben-UID: Microsoft. Quantum. Concepts. Pauli MS. author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuell No-Loc:</span><span class="sxs-lookup"><span data-stu-id="23c6f-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="23c6f-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="23c6f-103">"Q#"</span></span>
- <span data-ttu-id="23c6f-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="23c6f-104">"$$v"</span></span>
- <span data-ttu-id="23c6f-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="23c6f-105">"$$"</span></span>
- <span data-ttu-id="23c6f-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="23c6f-106">"$$"</span></span>
- <span data-ttu-id="23c6f-107">"$"</span><span class="sxs-lookup"><span data-stu-id="23c6f-107">"$"</span></span>
- <span data-ttu-id="23c6f-108">"$"</span><span class="sxs-lookup"><span data-stu-id="23c6f-108">"$"</span></span>
- <span data-ttu-id="23c6f-109">"$"</span><span class="sxs-lookup"><span data-stu-id="23c6f-109">"$"</span></span>
- <span data-ttu-id="23c6f-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="23c6f-110">"$$"</span></span>
- <span data-ttu-id="23c6f-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="23c6f-111">"\cdots"</span></span>
- <span data-ttu-id="23c6f-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="23c6f-112">"bmatrix"</span></span>
- <span data-ttu-id="23c6f-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="23c6f-113">"\ddots"</span></span>
- <span data-ttu-id="23c6f-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="23c6f-114">"\equiv"</span></span>
- <span data-ttu-id="23c6f-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="23c6f-115">"\sum"</span></span>
- <span data-ttu-id="23c6f-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="23c6f-116">"\begin"</span></span>
- <span data-ttu-id="23c6f-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="23c6f-117">"\end"</span></span>
- <span data-ttu-id="23c6f-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="23c6f-118">"\sqrt"</span></span>
- <span data-ttu-id="23c6f-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="23c6f-119">"\otimes"</span></span>
- <span data-ttu-id="23c6f-120">"{"</span><span class="sxs-lookup"><span data-stu-id="23c6f-120">"{"</span></span>
- <span data-ttu-id="23c6f-121">"}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-121">"}"</span></span>
- <span data-ttu-id="23c6f-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="23c6f-122">"\text"</span></span>
- <span data-ttu-id="23c6f-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="23c6f-123">"\phi"</span></span>
- <span data-ttu-id="23c6f-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="23c6f-124">"\kappa"</span></span>
- <span data-ttu-id="23c6f-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="23c6f-125">"\psi"</span></span>
- <span data-ttu-id="23c6f-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="23c6f-126">"\alpha"</span></span>
- <span data-ttu-id="23c6f-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="23c6f-127">"\beta"</span></span>
- <span data-ttu-id="23c6f-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="23c6f-128">"\gamma"</span></span>
- <span data-ttu-id="23c6f-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="23c6f-129">"\delta"</span></span>
- <span data-ttu-id="23c6f-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="23c6f-130">"\omega"</span></span>
- <span data-ttu-id="23c6f-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="23c6f-131">"\bra"</span></span>
- <span data-ttu-id="23c6f-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="23c6f-132">"\ket"</span></span>
- <span data-ttu-id="23c6f-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="23c6f-133">"\boldone"</span></span>
- <span data-ttu-id="23c6f-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="23c6f-134">"\\\\"</span></span>
- <span data-ttu-id="23c6f-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="23c6f-135">"\\"</span></span>
- <span data-ttu-id="23c6f-136">"="</span><span class="sxs-lookup"><span data-stu-id="23c6f-136">"="</span></span>
- <span data-ttu-id="23c6f-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="23c6f-137">"\frac"</span></span>
- <span data-ttu-id="23c6f-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="23c6f-138">"\text"</span></span>
- <span data-ttu-id="23c6f-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="23c6f-139">"\mapsto"</span></span>
- <span data-ttu-id="23c6f-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="23c6f-140">"\dagger"</span></span>
- <span data-ttu-id="23c6f-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="23c6f-141">"\to"</span></span>
- <span data-ttu-id="23c6f-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-142">"\begin{cases}"</span></span>
- <span data-ttu-id="23c6f-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-143">"\end{cases}"</span></span>
- <span data-ttu-id="23c6f-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="23c6f-144">"\operatorname"</span></span>
- <span data-ttu-id="23c6f-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="23c6f-145">"\braket"</span></span>
- <span data-ttu-id="23c6f-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="23c6f-146">"\id"</span></span>
- <span data-ttu-id="23c6f-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="23c6f-147">"\expect"</span></span>
- <span data-ttu-id="23c6f-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="23c6f-148">"\defeq"</span></span>
- <span data-ttu-id="23c6f-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="23c6f-149">"\variance"</span></span>
- <span data-ttu-id="23c6f-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="23c6f-150">"\dd"</span></span>
- <span data-ttu-id="23c6f-151">"&"</span><span class="sxs-lookup"><span data-stu-id="23c6f-151">"&"</span></span>
- <span data-ttu-id="23c6f-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-152">"\begin{align}"</span></span>
- <span data-ttu-id="23c6f-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-153">"\end{align}"</span></span>
- <span data-ttu-id="23c6f-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="23c6f-154">"\Lambda"</span></span>
- <span data-ttu-id="23c6f-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="23c6f-155">"\lambda"</span></span>
- <span data-ttu-id="23c6f-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="23c6f-156">"\Omega"</span></span>
- <span data-ttu-id="23c6f-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="23c6f-157">"\mathrm"</span></span>
- <span data-ttu-id="23c6f-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="23c6f-158">"\left"</span></span>
- <span data-ttu-id="23c6f-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="23c6f-159">"\right"</span></span>
- <span data-ttu-id="23c6f-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="23c6f-160">"\qquad"</span></span>
- <span data-ttu-id="23c6f-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="23c6f-161">"\times"</span></span>
- <span data-ttu-id="23c6f-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="23c6f-162">"\big"</span></span>
- <span data-ttu-id="23c6f-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="23c6f-163">"\langle"</span></span>
- <span data-ttu-id="23c6f-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="23c6f-164">"\rangle"</span></span>
- <span data-ttu-id="23c6f-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="23c6f-165">"\bigg"</span></span>
- <span data-ttu-id="23c6f-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="23c6f-166">"\Big"</span></span>
- <span data-ttu-id="23c6f-167">"|"</span><span class="sxs-lookup"><span data-stu-id="23c6f-167">"|"</span></span>
- <span data-ttu-id="23c6f-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="23c6f-168">"\mathbb"</span></span>
- <span data-ttu-id="23c6f-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="23c6f-169">"\vec"</span></span>
- <span data-ttu-id="23c6f-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="23c6f-170">"\in"</span></span>
- <span data-ttu-id="23c6f-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="23c6f-171">"\texttt"</span></span>
- <span data-ttu-id="23c6f-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="23c6f-172">"\ne"</span></span>
- <span data-ttu-id="23c6f-173">"<"</span><span class="sxs-lookup"><span data-stu-id="23c6f-173">"<"</span></span>
- <span data-ttu-id="23c6f-174">">"</span><span class="sxs-lookup"><span data-stu-id="23c6f-174">">"</span></span>
- <span data-ttu-id="23c6f-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="23c6f-175">"\leq"</span></span>
- <span data-ttu-id="23c6f-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="23c6f-176">"\geq"</span></span>
- <span data-ttu-id="23c6f-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="23c6f-177">"~~"</span></span>
- <span data-ttu-id="23c6f-178">"~"</span><span class="sxs-lookup"><span data-stu-id="23c6f-178">"~"</span></span>
- <span data-ttu-id="23c6f-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="23c6f-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="23c6f-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="23c6f-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="23c6f-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="23c6f-182">Pauli mått</span><span class="sxs-lookup"><span data-stu-id="23c6f-182">Pauli Measurements</span></span>

<span data-ttu-id="23c6f-183">I de föregående diskussionerna har vi fokuserat på beräknings bas mått.</span><span class="sxs-lookup"><span data-stu-id="23c6f-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="23c6f-184">I själva verket finns det andra vanliga mätningar som sker i den Quantum-bearbetningen som, från ett och samma perspektiv, är praktiska att uttrycka när det gäller beräknings bas mått.</span><span class="sxs-lookup"><span data-stu-id="23c6f-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="23c6f-185">När du arbetar med Q# , är den vanligaste typen av mätningar som du kommer att köra i troligen *Pauli mätningar*, som generaliserar beräknings bas mått för att ta med mätningar i andra baser och paritet mellan olika qubits.</span><span class="sxs-lookup"><span data-stu-id="23c6f-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="23c6f-186">I sådana fall är det vanligt att diskutera en Pauli-operatör i allmänhet en operator som $ X, Y, z $ eller $ z \otimes z, x \otimes x, x \otimes Y $ och så vidare.</span><span class="sxs-lookup"><span data-stu-id="23c6f-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span> 

> [!TIP]
<span data-ttu-id="23c6f-187">> I Q# , representeras qubit Pauli-operatörer vanligt vis av matriser av typen `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="23c6f-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="23c6f-188">> Om du till exempel vill representera $ X \otimes Z \otimes Y $ kan du använda matrisen `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="23c6f-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="23c6f-189">Att diskutera mått i Pauli-operatörer är särskilt vanligt i underfältet för en Quantum-fel korrigering.</span><span class="sxs-lookup"><span data-stu-id="23c6f-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="23c6f-190">I Q# följer vi en liknande konvention. vi förklarar nu den här alternativa vyn av mått.</span><span class="sxs-lookup"><span data-stu-id="23c6f-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="23c6f-191">Innan du går in på Detaljer om hur du kan tänka på en Pauli-mätning, är det bra att tänka på vad som mäter en enskild qubit i en Quantum-dator till Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="23c6f-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="23c6f-192">Tänk dig att vi har ett $ n $ -qubit Quantum-tillstånd, och sedan mäter du en qubit omedelbart ut hälften av de $ 2 ^ n- $ möjligheter som tillstånden kan ha.</span><span class="sxs-lookup"><span data-stu-id="23c6f-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="23c6f-193">Med andra ord mäter måttet Quantum-tillstånd till ett av två halva blank steg.</span><span class="sxs-lookup"><span data-stu-id="23c6f-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="23c6f-194">Vi kan generalisera det sätt vi tycker att mäta för att återspegla den här intuition.</span><span class="sxs-lookup"><span data-stu-id="23c6f-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="23c6f-195">För att kortfattat identifiera dessa under utrymmen behöver vi ett språk för att beskriva dem.</span><span class="sxs-lookup"><span data-stu-id="23c6f-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="23c6f-196">Ett sätt att beskriva två under utrymmen är genom att ange dem via en matris som bara har två unika Eigenvalues, som tas av en konvention som ska vara $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="23c6f-197">Ett enkelt exempel på hur du kan beskriva under utrymmen på det här sättet är att tänka på $ Z $ :</span><span class="sxs-lookup"><span data-stu-id="23c6f-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="23c6f-198">Z & = \begin{bmatrix} 1 & 0 \\\\ & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="23c6f-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="23c6f-199">Genom att läsa de diagonala elementen i Pauli- $ Z- $ matrisen kan vi se att $ Z $ har två eigenvectors, $ \ket { 0 } $ och $ \ket { 1 } $ , med motsvarande Eigenvalues $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="23c6f-200">Om vi mäter qubit och hämtar `Zero` (som motsvarar tillstånd $ \ket { 0 } $ ) vet vi att situationen för vår qubit är a $ + 1 $ eigenstate av $ Z- $ operatorn.</span><span class="sxs-lookup"><span data-stu-id="23c6f-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="23c6f-201">På samma sätt `One` vet vi att vår qubit-stat är en $ -1 $ eigenstate av $ Z $ . Den här processen kallas för Pauli-mått som "mäta Pauli $ Z $ " och är helt likvärdig med att utföra en beräknings bas mätning.</span><span class="sxs-lookup"><span data-stu-id="23c6f-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="23c6f-202">$2 \times 2- $ matriser som är en enhetlig omvandling av $ Z $ uppfyller också det här kriteriet.</span><span class="sxs-lookup"><span data-stu-id="23c6f-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="23c6f-203">Det innebär att vi också kan använda en matris $ a = u ^ \dagger Z u $ , där $ u $ är en annan enhetlig matris, för att ge en matris som definierar de två resultatet av en mätning i dess $ \pm 1- $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="23c6f-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="23c6f-204">Pauli-mätningarna hänvisar till den enhetliga motsvarigheten genom $ att identifiera X, Y, Z- $ mått som likvärdiga mätningar som en kan göra för att få information från en qubit.</span><span class="sxs-lookup"><span data-stu-id="23c6f-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="23c6f-205">De här måtten anges nedan för bekvämlighet.</span><span class="sxs-lookup"><span data-stu-id="23c6f-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="23c6f-206">|Pauli mått-  | transformering  |</span><span class="sxs-lookup"><span data-stu-id="23c6f-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="23c6f-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="23c6f-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="23c6f-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="23c6f-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="23c6f-209">|$ $ Y | $HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="23c6f-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="23c6f-210">Med det här språket är "mått $ Y $ " detsamma som att tillämpa $ HS ^ \dagger $ och sedan mäta beräknings grunden, där [`S`](xref:Microsoft.Quantum.Intrinsic.S) är en inbyggd Quantum-åtgärd som ibland kallas "fas grind" och kan simuleras av den enhetliga matrisen</span><span class="sxs-lookup"><span data-stu-id="23c6f-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:Microsoft.Quantum.Intrinsic.S) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="23c6f-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="23c6f-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="23c6f-212">1 & 0 \\\\ 0 & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="23c6f-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="23c6f-213">Det är också detsamma som att tillämpa $ HS ^ \dagger $ på Vectorn för Quantum-tillstånd och sedan mäta $ Z $ , så att följande åtgärd motsvarar `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="23c6f-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```qsharp
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="23c6f-214">Rätt tillstånd kan sedan hittas genom att omvandla tillbaka till beräknings grunden, vilka belopp som ska tillämpas på den $ Quantum- $ delstats vektorn. i ovanstående kodfragment hanteras omvandlingen tillbaka till beräknings basen automatiskt av användningen av `within … apply` blocket.</span><span class="sxs-lookup"><span data-stu-id="23c6f-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="23c6f-215">I Q# säger vi resultatet---det vill, den klassiska information som extraheras från att samverka med tillstånds---anges av ett `Result` värde $ j \in \\ { \texttt { noll } , \texttt { ett } \\ } $ som anger om resultatet är i $ (-1) ^ j $ eigenspace i Pauli-operatorn uppmätt.</span><span class="sxs-lookup"><span data-stu-id="23c6f-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="23c6f-216">Flera qubit-mått</span><span class="sxs-lookup"><span data-stu-id="23c6f-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="23c6f-217">Mätningar av multi-qubit Pauli-operatörer definieras på samma sätt som de visas på:</span><span class="sxs-lookup"><span data-stu-id="23c6f-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="23c6f-218">Z z 1 0 0-1 0-1 0 – 1 0 0 0 0 \otimes = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & 1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="23c6f-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="23c6f-219">Det innebär att behållna produkter av två Pauli- $ ö- $ operatörer utgör en matris som består av två blank steg bestående av $ + 1 $ och $ -1 $ Eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="23c6f-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="23c6f-220">Precis som med ett qubit-fall utgör både ett halvt utrymme att hälften av det tillgängliga vektor utrymmet tillhör $ + 1 $ eigenspace och den återstående halvan till $ -1- $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="23c6f-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="23c6f-221">I allmänhet är det enkelt att se från definitionen av den beskrivande produkten som alla beskrivare produkter av Pauli- $ ö- $ operatörer och identiteten följer.</span><span class="sxs-lookup"><span data-stu-id="23c6f-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="23c6f-222">Exempel:</span><span class="sxs-lookup"><span data-stu-id="23c6f-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="23c6f-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="23c6f-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="23c6f-224">1 &  0 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="23c6f-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="23c6f-226">0 &  0 & -1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="23c6f-227">0 &  0 & & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="23c6f-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="23c6f-228">Precis som tidigare beskriver en enhetlig omvandling av sådana matriser även två hälften-blank steg som är märkta med $ \pm 1 $ Eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="23c6f-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="23c6f-229">Till exempel $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  från den identitet som Z- $ = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="23c6f-230">På samma sätt som med ett-qubit-fall kan alla qubits Pauli-mått skrivas som $ u ^ \dagger (Z \otimes \id ) u $ för $ 4 4 höga \times $ matriser $ U $ . Vi räknar upp omvandlingarna i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="23c6f-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="23c6f-231">>I tabellen nedan använder vi $ \operatorname { swap } $ för att ange matrisen >$$</span><span class="sxs-lookup"><span data-stu-id="23c6f-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="23c6f-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="23c6f-232">> \begin{align}</span></span>
<span data-ttu-id="23c6f-233">>     \operatorname{Växla } &=</span><span class="sxs-lookup"><span data-stu-id="23c6f-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="23c6f-234">>     \left( \begin { matris}</span><span class="sxs-lookup"><span data-stu-id="23c6f-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="23c6f-235">>         1 & 0 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="23c6f-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="23c6f-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="23c6f-238">>0 & 0 & 0 & 1 > \end { matris } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="23c6f-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="23c6f-239">> $$</span><span class="sxs-lookup"><span data-stu-id="23c6f-239">> $$</span></span>
<span data-ttu-id="23c6f-240">> används för att simulera den inbyggda åtgärden [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="23c6f-240">> used to simulate the intrinsic operation [`SWAP`](xref:Microsoft.Quantum.Intrinsic).</span></span>

<span data-ttu-id="23c6f-241">|Pauli mått-     | transformering  |</span><span class="sxs-lookup"><span data-stu-id="23c6f-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="23c6f-242">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="23c6f-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="23c6f-243">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="23c6f-244">|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="23c6f-245">|$\boldone \otimes Z- $ | $ \operatorname { växling } $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="23c6f-246">|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { växling } $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="23c6f-247">|$\boldone \otimes Y $ | $ - \dagger \otimes \boldone \operatorname { växling } (HS ^ $ )|</span><span class="sxs-lookup"><span data-stu-id="23c6f-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="23c6f-248">|$Z \otimes Z- $ | $ \operatorname { CNOT } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="23c6f-249">|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="23c6f-250">|$Y \otimes Z $ | $ \operatorname { } \_ { -CNOT 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="23c6f-251">|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="23c6f-252">|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="23c6f-253">|$Y \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="23c6f-254">|$Z \otimes Y $ | $ \operatorname { } \_ { -CNOT 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="23c6f-255">|$X \otimes Y $ | $ \operatorname { } \_ { -CNOT 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="23c6f-256">|$Y \otimes Y $ | $ \operatorname { } \_ { -CNOT 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="23c6f-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="23c6f-257">Här [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) visas åtgärden av följande skäl.</span><span class="sxs-lookup"><span data-stu-id="23c6f-257">Here, the [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operation appears for the following reason.</span></span>
<span data-ttu-id="23c6f-258">Varje Pauli-mått som inte omfattar $ \boldone $ matrisen motsvarar en enhetlig till $ z \otimes z $ av ovanstående orsaker.</span><span class="sxs-lookup"><span data-stu-id="23c6f-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="23c6f-259">Eigenvalues av $ z \otimes z $ är bara beroende av pariteten för qubits som utgör varje beräknings bas vektor och de kontrollerade-inte-åtgärderna kan beräkna denna paritet och lagra den i den första biten.</span><span class="sxs-lookup"><span data-stu-id="23c6f-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="23c6f-260">När den första biten mäts kan vi återställa identiteten för det resulterande halva utrymmet, vilket motsvarar att mäta Pauli-operatorn.</span><span class="sxs-lookup"><span data-stu-id="23c6f-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="23c6f-261">Ytterligare en anmärkning: det kan vara frestande att anta att måttet $ z \otimes z $ är detsamma som att mäta $ z \otimes \mathbb { 1 } $ och sedan $ \mathbb { 1 } \otimes Z $ . Detta antagande skulle vara falskt.</span><span class="sxs-lookup"><span data-stu-id="23c6f-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="23c6f-262">Orsaken är att $ z z- \otimes $ projekt har ett Quantum-tillstånd i antingen $ eigenstate + 1 $ eller $ -1 $ för dessa operatörer.</span><span class="sxs-lookup"><span data-stu-id="23c6f-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="23c6f-263">Mätning $ \otimes \mathbb { av z 1 } $ och sedan $ \mathbb { 1 } \otimes z- $ projekt är den Quantum-tillstånds vektorn först i ett halvt utrymme på $ z \otimes \mathbb { 1 } $ och sedan till ett halvt utrymme på $ \mathbb { 1 } \otimes Z $ . Eftersom det finns fyra beräknings bas vektorer minskar statusen till ett kvartals utrymme och minskar därför den till en enda beräknings bas vektor.</span><span class="sxs-lookup"><span data-stu-id="23c6f-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="23c6f-264">Korrelationer mellan qubitar</span><span class="sxs-lookup"><span data-stu-id="23c6f-264">Correlations between qubits</span></span>
<span data-ttu-id="23c6f-265">Ett annat sätt att titta på mätnings behållar produkter av Pauli-matriser som $ X \otimes x $ eller $ z \otimes z $ är att dessa mätningar gör att du kan titta på information som lagras i korrelationerna mellan de två qubits.</span><span class="sxs-lookup"><span data-stu-id="23c6f-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="23c6f-266">Med måttet $ X \otimes \id $ kan du titta på information som lagras lokalt i den första qubit.</span><span class="sxs-lookup"><span data-stu-id="23c6f-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="23c6f-267">Även om båda typerna av mätningar är lika värdefulla i Quantum Computing, lyser den tidigare kraften i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="23c6f-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="23c6f-268">Det visar att i Quantum Computing är ofta den information som du vill lära inte lagrad i en enskild qubit utan att i stället lagras lokalt i alla qubits samtidigt, och därför bara genom att titta på den via en gemensam mätning (t. ex. $ z \otimes z $ ) blir den här informationen manifest.</span><span class="sxs-lookup"><span data-stu-id="23c6f-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="23c6f-269">I fel korrigering vill vi till exempel ofta lära sig vilket fel som har inträffat och lära mig ingenting om det tillstånd som vi försöker skydda.</span><span class="sxs-lookup"><span data-stu-id="23c6f-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="23c6f-270">[Kod exemplet bit-flip](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) visar ett exempel på hur du kan göra det med hjälp av mätningar som $ z \otimes z \otimes \id $ och $ \id \otimes z \otimes z $ . < ! --Att göra: ändra detta till en länk till exempel webbläsaren så snart kod exemplet för bit-Flip är på skiva.</span><span class="sxs-lookup"><span data-stu-id="23c6f-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="23c6f-271">Godtyckliga Pauli-operatorer som $ X \otimes Y \otimes Z \otimes \boldone $ kan också mätas.</span><span class="sxs-lookup"><span data-stu-id="23c6f-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="23c6f-272">Alla sådana Beslags produkter av Pauli-operatörer har bara två Eigenvalues- $ \pm 1 $ och båda eigenspaces utgörs av halva utrymmet i hela vektor utrymmet.</span><span class="sxs-lookup"><span data-stu-id="23c6f-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="23c6f-273">De sammanfaller därför med de krav som anges ovan.</span><span class="sxs-lookup"><span data-stu-id="23c6f-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="23c6f-274">I Q# kan sådana mätningar returnera $ j $ om mätningen ger ett resultat i eigenspace $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="23c6f-275">Att ha Pauli mätningar som en inbyggd funktion i Q# är till hjälp eftersom du kan mäta sådana operatörer som kräver långa kedjor av kontrollerade, icke-portar och bas omvandlingar för att beskriva hur mycket $ U-grind som $ krävs för att uttrycka åtgärden som en beskrivare produkt i $ Z $ och $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="23c6f-276">Genom att kunna ange att du vill göra en av dessa fördefinierade mätningar behöver du inte oroa dig för att du ska kunna omvandla din grund till att en beräknings bas mätning ger nödvändig information.</span><span class="sxs-lookup"><span data-stu-id="23c6f-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="23c6f-277">Q# hanterar alla transformeringar som behövs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="23c6f-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="23c6f-278">Mer information finns i [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) åtgärderna och.</span><span class="sxs-lookup"><span data-stu-id="23c6f-278">For more information, see the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) and [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="23c6f-279">No-Cloning satsen</span><span class="sxs-lookup"><span data-stu-id="23c6f-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="23c6f-280">Quantum-informationen är kraftfull.</span><span class="sxs-lookup"><span data-stu-id="23c6f-280">Quantum information is powerful.</span></span>
<span data-ttu-id="23c6f-281">Det gör det möjligt för oss att göra fantastiska saker som faktor tal exponentiellt snabbare än de bästa kända klassiska algoritmerna, eller att effektivt simulera korrelerade Electron-system som klassiska kräver exponentiell kostnad för att simulera korrekt.</span><span class="sxs-lookup"><span data-stu-id="23c6f-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="23c6f-282">Det finns dock begränsningar för kraften i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="23c6f-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="23c6f-283">En sådan begränsning anges av *satsen No-kloningsing*.</span><span class="sxs-lookup"><span data-stu-id="23c6f-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="23c6f-284">No-Cloning-satsen är aptly med namnet.</span><span class="sxs-lookup"><span data-stu-id="23c6f-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="23c6f-285">Den tillåter inte kloning av generiska Quantum-tillstånd av en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="23c6f-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="23c6f-286">Satsen-beviset är remarkably är enkelt.</span><span class="sxs-lookup"><span data-stu-id="23c6f-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="23c6f-287">Det fullständiga beviset på No-kloning-satsen är lite för tekniskt för vår diskussion här, men beviset för att det inte finns några ytterligare hjälp qubits finns i vår omfattning.</span><span class="sxs-lookup"><span data-stu-id="23c6f-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope.</span></span>

<span data-ttu-id="23c6f-288">För en sådan Quantum-dator måste klonings åtgärden beskrivas av en enhetlig matris.</span><span class="sxs-lookup"><span data-stu-id="23c6f-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="23c6f-289">Vi tillåter inte mätningar, eftersom det skulle skada det Quantum-tillstånd som vi försöker klona.</span><span class="sxs-lookup"><span data-stu-id="23c6f-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="23c6f-290">För att simulera klonings åtgärden vill vi att den enhetliga matrisen som används för att ha den egenskap som $$</span><span class="sxs-lookup"><span data-stu-id="23c6f-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="23c6f-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="23c6f-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="23c6f-292">för alla tillstånd $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="23c6f-293">Egenskapen linearitet för mat ris multiplikation anger sedan att för andra Quantum $ \ket { \phi } $ -tillstånd.</span><span class="sxs-lookup"><span data-stu-id="23c6f-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="23c6f-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="23c6f-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="23c6f-295">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="23c6f-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="23c6f-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="23c6f-297">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="23c6f-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="23c6f-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="23c6f-298">\right) \\\\</span></span>
    <span data-ttu-id="23c6f-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).</span><span class="sxs-lookup"><span data-stu-id="23c6f-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="23c6f-300">Detta ger den grundläggande intuition bakom No-Cloning satsen: alla enheter som kopierar ett okänt Quantum-tillstånd måste orsaka fel på minst några av de tillstånd som den kopierar.</span><span class="sxs-lookup"><span data-stu-id="23c6f-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="23c6f-301">Den nyckel som förutsätter att Klonaren fungerar linjärt i indata-läget kan brytas genom addition och mätning av hjälp-qubits, men sådana interaktioner läcker också information om systemet genom mätnings statistiken och förhindrar exakt kloning i sådana fall.</span><span class="sxs-lookup"><span data-stu-id="23c6f-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="23c6f-302">Mer information om No-Cloning satsen finns i mer [information](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="23c6f-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="23c6f-303">No-Cloning satsen är viktigt för att ge kvalitativ förståelse för Quantum Computing, eftersom om du skulle kunna klona Quantum-tillstånd på ett mycket bra ställe skulle du få en Magical möjlighet att lära sig från Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="23c6f-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="23c6f-304">I själva verket kan du bryta mot Heisenbergs vaunted osäkerhets princip.</span><span class="sxs-lookup"><span data-stu-id="23c6f-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="23c6f-305">Alternativt kan du använda en optimal klonare för att ta ett enda exempel från en komplex Quantum-distribution och lära dig allt du kan behöva lära dig mer om distributionen från bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="23c6f-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="23c6f-306">Detta skulle vara precis som du vänder på en och samma som när du säger upp en vän om resultatet med att de svarar "Ah-fördelningen av dessa mynt måste vara Bernoulli med $ p = 0.512643 \ ldots $ !"</span><span class="sxs-lookup"><span data-stu-id="23c6f-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="23c6f-307">En sådan instruktion skulle vara icke-sensical eftersom en bit av information (resultatet av huvudena) inte kan ge de många bitar av information som krävs för att koda distributionen utan avsevärd tidigare information.</span><span class="sxs-lookup"><span data-stu-id="23c6f-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="23c6f-308">På samma sätt kan vi inte helt klona ett Quantum-tillstånd på samma sätt som vi inte kan förbereda en ensemble av sådana mynt utan att veta $ p $ .</span><span class="sxs-lookup"><span data-stu-id="23c6f-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="23c6f-309">Informationen är inte kostnads fri i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="23c6f-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="23c6f-310">Varje qubit uppmätta ger en enskild bit av information och No-Cloning satsen visar att det inte finns några bakdörr som kan utnyttjas för att komma runt den grundläggande kompromissen mellan information som har vunnits i systemet och den störning som har påbörjats.</span><span class="sxs-lookup"><span data-stu-id="23c6f-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
