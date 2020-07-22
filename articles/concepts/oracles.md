---
<span data-ttu-id="921c9-101">title: Quantum Oracle-Beskrivning: Lär dig hur du arbetar med och definierar Quantum Oracles, svarta Box-åtgärder som används som inmatade i en annan algoritm.</span><span class="sxs-lookup"><span data-stu-id="921c9-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="921c9-102">författare: cgranade UID: Microsoft. Quantum. Concepts. Oracles MS. author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 MS. topic: artikeln No-Loc:</span><span class="sxs-lookup"><span data-stu-id="921c9-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="921c9-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="921c9-103">"$$"</span></span>
- <span data-ttu-id="921c9-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="921c9-104">"$$"</span></span>
- <span data-ttu-id="921c9-105">"$"</span><span class="sxs-lookup"><span data-stu-id="921c9-105">"$"</span></span>
- <span data-ttu-id="921c9-106">"$"</span><span class="sxs-lookup"><span data-stu-id="921c9-106">"$"</span></span>
- <span data-ttu-id="921c9-107">"$"</span><span class="sxs-lookup"><span data-stu-id="921c9-107">"$"</span></span>
- <span data-ttu-id="921c9-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="921c9-108">"$$"</span></span>
- <span data-ttu-id="921c9-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="921c9-109">"\cdots"</span></span>
- <span data-ttu-id="921c9-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="921c9-110">"bmatrix"</span></span>
- <span data-ttu-id="921c9-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="921c9-111">"\ddots"</span></span>
- <span data-ttu-id="921c9-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="921c9-112">"\equiv"</span></span>
- <span data-ttu-id="921c9-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="921c9-113">"\sum"</span></span>
- <span data-ttu-id="921c9-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="921c9-114">"\begin"</span></span>
- <span data-ttu-id="921c9-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="921c9-115">"\end"</span></span>
- <span data-ttu-id="921c9-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="921c9-116">"\sqrt"</span></span>
- <span data-ttu-id="921c9-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="921c9-117">"\otimes"</span></span>
- <span data-ttu-id="921c9-118">"{"</span><span class="sxs-lookup"><span data-stu-id="921c9-118">"{"</span></span>
- <span data-ttu-id="921c9-119">"}"</span><span class="sxs-lookup"><span data-stu-id="921c9-119">"}"</span></span>
- <span data-ttu-id="921c9-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="921c9-120">"\text"</span></span>
- <span data-ttu-id="921c9-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="921c9-121">"\phi"</span></span>
- <span data-ttu-id="921c9-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="921c9-122">"\kappa"</span></span>
- <span data-ttu-id="921c9-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="921c9-123">"\psi"</span></span>
- <span data-ttu-id="921c9-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="921c9-124">"\alpha"</span></span>
- <span data-ttu-id="921c9-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="921c9-125">"\beta"</span></span>
- <span data-ttu-id="921c9-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="921c9-126">"\gamma"</span></span>
- <span data-ttu-id="921c9-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="921c9-127">"\delta"</span></span>
- <span data-ttu-id="921c9-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="921c9-128">"\omega"</span></span>
- <span data-ttu-id="921c9-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="921c9-129">"\bra"</span></span>
- <span data-ttu-id="921c9-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="921c9-130">"\ket"</span></span>
- <span data-ttu-id="921c9-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="921c9-131">"\boldone"</span></span>
- <span data-ttu-id="921c9-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="921c9-132">"\\\\"</span></span>
- <span data-ttu-id="921c9-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="921c9-133">"\\"</span></span>
- <span data-ttu-id="921c9-134">"="</span><span class="sxs-lookup"><span data-stu-id="921c9-134">"="</span></span>
- <span data-ttu-id="921c9-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="921c9-135">"\frac"</span></span>
- <span data-ttu-id="921c9-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="921c9-136">"\text"</span></span>
- <span data-ttu-id="921c9-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="921c9-137">"\mapsto"</span></span>
- <span data-ttu-id="921c9-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="921c9-138">"\dagger"</span></span>
- <span data-ttu-id="921c9-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="921c9-139">"\to"</span></span>
- <span data-ttu-id="921c9-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="921c9-140">"\begin{cases}"</span></span>
- <span data-ttu-id="921c9-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="921c9-141">"\end{cases}"</span></span>
- <span data-ttu-id="921c9-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="921c9-142">"\operatorname"</span></span>
- <span data-ttu-id="921c9-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="921c9-143">"\braket"</span></span>
- <span data-ttu-id="921c9-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="921c9-144">"\id"</span></span>
- <span data-ttu-id="921c9-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="921c9-145">"\expect"</span></span>
- <span data-ttu-id="921c9-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="921c9-146">"\defeq"</span></span>
- <span data-ttu-id="921c9-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="921c9-147">"\variance"</span></span>
- <span data-ttu-id="921c9-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="921c9-148">"\dd"</span></span>
- <span data-ttu-id="921c9-149">"&"</span><span class="sxs-lookup"><span data-stu-id="921c9-149">"&"</span></span>
- <span data-ttu-id="921c9-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="921c9-150">"\begin{align}"</span></span>
- <span data-ttu-id="921c9-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="921c9-151">"\end{align}"</span></span>
- <span data-ttu-id="921c9-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="921c9-152">"\Lambda"</span></span>
- <span data-ttu-id="921c9-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="921c9-153">"\lambda"</span></span>
- <span data-ttu-id="921c9-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="921c9-154">"\Omega"</span></span>
- <span data-ttu-id="921c9-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="921c9-155">"\mathrm"</span></span>
- <span data-ttu-id="921c9-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="921c9-156">"\left"</span></span>
- <span data-ttu-id="921c9-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="921c9-157">"\right"</span></span>
- <span data-ttu-id="921c9-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="921c9-158">"\qquad"</span></span>
- <span data-ttu-id="921c9-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="921c9-159">"\times"</span></span>
- <span data-ttu-id="921c9-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="921c9-160">"\big"</span></span>
- <span data-ttu-id="921c9-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="921c9-161">"\langle"</span></span>
- <span data-ttu-id="921c9-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="921c9-162">"\rangle"</span></span>
- <span data-ttu-id="921c9-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="921c9-163">"\bigg"</span></span>
- <span data-ttu-id="921c9-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="921c9-164">"\Big"</span></span>
- <span data-ttu-id="921c9-165">"|"</span><span class="sxs-lookup"><span data-stu-id="921c9-165">"|"</span></span>
- <span data-ttu-id="921c9-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="921c9-166">"\mathbb"</span></span>
- <span data-ttu-id="921c9-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="921c9-167">"\vec"</span></span>
- <span data-ttu-id="921c9-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="921c9-168">"\in"</span></span>
- <span data-ttu-id="921c9-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="921c9-169">"\texttt"</span></span>
- <span data-ttu-id="921c9-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="921c9-170">"\ne"</span></span>
- <span data-ttu-id="921c9-171">"<"</span><span class="sxs-lookup"><span data-stu-id="921c9-171">"<"</span></span>
- <span data-ttu-id="921c9-172">">"</span><span class="sxs-lookup"><span data-stu-id="921c9-172">">"</span></span>
- <span data-ttu-id="921c9-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="921c9-173">"\leq"</span></span>
- <span data-ttu-id="921c9-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="921c9-174">"\geq"</span></span>
- <span data-ttu-id="921c9-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="921c9-175">"~~"</span></span>
- <span data-ttu-id="921c9-176">"~"</span><span class="sxs-lookup"><span data-stu-id="921c9-176">"~"</span></span>
- <span data-ttu-id="921c9-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="921c9-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="921c9-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="921c9-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="921c9-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="921c9-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="921c9-180">Quantum Oracle</span><span class="sxs-lookup"><span data-stu-id="921c9-180">Quantum Oracles</span></span>

<span data-ttu-id="921c9-181">En Oracle $ O $ är en "svart box"-åtgärd som används som inmatad till en annan algoritm.</span><span class="sxs-lookup"><span data-stu-id="921c9-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="921c9-182">Ofta definieras sådana åtgärder med hjälp av en klassisk funktion $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ som tar en $ n $ -bitars binär indata och producerar en $ m $ -bitars binär utdata.</span><span class="sxs-lookup"><span data-stu-id="921c9-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="921c9-183">Det gör du genom att tänka på ett visst binärt $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="921c9-184">Vi kan märka qubit tillstånd som $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="921c9-185">Vi kan först försöka definiera $ o $ så att $ o \ket { x } = \ket { f (x) } $ , men det har ett par problem.</span><span class="sxs-lookup"><span data-stu-id="921c9-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="921c9-186">För $ det första $ kan f ha olika storlekar på indata och utdata ( $ n \ne m $ ), som att tillämpa $ O $ skulle ändra antalet qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="921c9-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="921c9-187">Andra, även om $ n = m $ , kanske funktionen inte är inverteras: om $ f (x) = f (y) $ för vissa $ x \ne y $ , så $ o \ket { x } = o y, \ket { } $ men $ o ^ o \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="921c9-188">Det innebär att vi inte kan skapa den angränsande åtgärden $ O ^ \dagger $ , och Oracle måste ha ett angränsande definierat för dem.</span><span class="sxs-lookup"><span data-stu-id="921c9-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="921c9-189">Definiera en Oracle genom att påverka beräknings bas staterna</span><span class="sxs-lookup"><span data-stu-id="921c9-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="921c9-190">Vi kan hantera båda dessa problem genom att introducera ett andra register av $ m $ qubits för att hålla vårt svar.</span><span class="sxs-lookup"><span data-stu-id="921c9-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="921c9-191">Därefter definierar vi resultatet av Oracle i alla beräknings grund lägen: för alla $ x \in \\ { 0, 1 \\ } ^ n $ och $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="921c9-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="921c9-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="921c9-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="921c9-193">Nu $ = \dagger $ måste vi ha löst båda de tidigare problemen.</span><span class="sxs-lookup"><span data-stu-id="921c9-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="921c9-194">Om du vill se den $ o ^ = { \dagger } $ 2-e-postmeddelandet som $ o ^ 2 = \boldone $ sedan $ en \oplus b-\oplus b = a $ för alla $ a, b \in \[ ! Öpp. NO-LOC ({)] 0, 1 \[ ! Öpp. NO-LOC (})] $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="921c9-195">Det innebär att $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="921c9-196">Det är viktigt att definiera en Oracle på det här sättet för varje beräknings bas status $ \ket { x } \ket { y } $ definierar också hur $ O $ fungerar för alla andra tillstånd.</span><span class="sxs-lookup"><span data-stu-id="921c9-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="921c9-197">Detta följer omedelbart från det faktum att $ O $ , precis som alla Quantum-åtgärder, är linjärt i det tillstånd som det fungerar på.</span><span class="sxs-lookup"><span data-stu-id="921c9-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="921c9-198">Överväg Hadamard-åtgärden, till exempel, som definieras av $ h \ket { 0 } = \ket { + } $ och $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="921c9-199">Om vi vill veta hur $ h $ agerar på $ \ket { + } $ kan vi använda den här $ H $ är linjär,</span><span class="sxs-lookup"><span data-stu-id="921c9-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="921c9-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="921c9-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="921c9-201">= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="921c9-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="921c9-202">Om du definierar vår Oracle $ O $ kan vi på samma sätt använda att alla tillstånd $ \ket { \psi } $ på $ n + m $ qubits kan skrivas som</span><span class="sxs-lookup"><span data-stu-id="921c9-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="921c9-203">{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="921c9-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="921c9-204">där $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ representerar koefficienterna för status $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="921c9-205">Därför</span><span class="sxs-lookup"><span data-stu-id="921c9-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="921c9-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="921c9-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="921c9-207">= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="921c9-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="921c9-208">Fas Oracle</span><span class="sxs-lookup"><span data-stu-id="921c9-208">Phase oracles</span></span>
<span data-ttu-id="921c9-209">Alternativt kan vi koda $ f $ till en Oracle- $ O $ genom att använda en _fas_ baserat på inmatat på $ O $ . Vi kan till exempel definiera $ O $ så att$$</span><span class="sxs-lookup"><span data-stu-id="921c9-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="921c9-210">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="921c9-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="921c9-211">Om en fas Oracle agerar i ett register inlednings vis i ett beräknings underlags tillstånd $ \ket { x } $ , är den här fasen en global fas och går därför inte att observera.</span><span class="sxs-lookup"><span data-stu-id="921c9-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="921c9-212">Men en sådan Oracle kan vara en mycket kraftfull resurs om den tillämpas på en överposition eller som en kontrollerad åtgärd.</span><span class="sxs-lookup"><span data-stu-id="921c9-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="921c9-213">Anta till exempel en fas Oracle- $ O_f $ för en qubit funktion $ f $ .</span><span class="sxs-lookup"><span data-stu-id="921c9-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="921c9-214">Dra$$</span><span class="sxs-lookup"><span data-stu-id="921c9-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="921c9-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="921c9-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="921c9-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="921c9-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="921c9-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="921c9-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="921c9-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="921c9-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="921c9-219">=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="921c9-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="921c9-220">I allmänhet kan båda vyerna i Oracle utökas för att representera klassiska funktioner som returnerar reella tal i stället för bara en enda bit.</span><span class="sxs-lookup"><span data-stu-id="921c9-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="921c9-221">Att välja det bästa sättet att implementera en Oracle är beroende av hur den här Oracle kommer att användas inom en specifik algoritm.</span><span class="sxs-lookup"><span data-stu-id="921c9-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="921c9-222">Till exempel är [Deutsch-Jozsa-algoritmen](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) beroende av den Oracle som implementerats på det första sättet, medan [algoritmen för Grover är](https://en.wikipedia.org/wiki/Grover's_algorithm) beroende av den Oracle som implementerats på det andra sättet.</span><span class="sxs-lookup"><span data-stu-id="921c9-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="921c9-223">För mer information, föreslår vi diskussionen i [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="921c9-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
