---
<span data-ttu-id="f5061-101">title: Quantum Oracle-Beskrivning: Lär dig hur du arbetar med och definierar Quantum Oracles, svarta Box-åtgärder som används som inmatade i en annan algoritm.</span><span class="sxs-lookup"><span data-stu-id="f5061-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="f5061-102">författare: cgranade-UID: Microsoft. Quantum. Concepts. Oracles MS. author: chgranad MS. Date: 07/11/2018 MS. topic: artikeln No-Loc:</span><span class="sxs-lookup"><span data-stu-id="f5061-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="f5061-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="f5061-103">"Q#"</span></span>
- <span data-ttu-id="f5061-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="f5061-104">"$$v"</span></span>
- <span data-ttu-id="f5061-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="f5061-105">"$$"</span></span>
- <span data-ttu-id="f5061-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="f5061-106">"$$"</span></span>
- <span data-ttu-id="f5061-107">"$"</span><span class="sxs-lookup"><span data-stu-id="f5061-107">"$"</span></span>
- <span data-ttu-id="f5061-108">"$"</span><span class="sxs-lookup"><span data-stu-id="f5061-108">"$"</span></span>
- <span data-ttu-id="f5061-109">"$"</span><span class="sxs-lookup"><span data-stu-id="f5061-109">"$"</span></span>
- <span data-ttu-id="f5061-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="f5061-110">"$$"</span></span>
- <span data-ttu-id="f5061-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="f5061-111">"\cdots"</span></span>
- <span data-ttu-id="f5061-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="f5061-112">"bmatrix"</span></span>
- <span data-ttu-id="f5061-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="f5061-113">"\ddots"</span></span>
- <span data-ttu-id="f5061-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="f5061-114">"\equiv"</span></span>
- <span data-ttu-id="f5061-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="f5061-115">"\sum"</span></span>
- <span data-ttu-id="f5061-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="f5061-116">"\begin"</span></span>
- <span data-ttu-id="f5061-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="f5061-117">"\end"</span></span>
- <span data-ttu-id="f5061-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="f5061-118">"\sqrt"</span></span>
- <span data-ttu-id="f5061-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="f5061-119">"\otimes"</span></span>
- <span data-ttu-id="f5061-120">"{"</span><span class="sxs-lookup"><span data-stu-id="f5061-120">"{"</span></span>
- <span data-ttu-id="f5061-121">"}"</span><span class="sxs-lookup"><span data-stu-id="f5061-121">"}"</span></span>
- <span data-ttu-id="f5061-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="f5061-122">"\text"</span></span>
- <span data-ttu-id="f5061-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="f5061-123">"\phi"</span></span>
- <span data-ttu-id="f5061-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="f5061-124">"\kappa"</span></span>
- <span data-ttu-id="f5061-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="f5061-125">"\psi"</span></span>
- <span data-ttu-id="f5061-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="f5061-126">"\alpha"</span></span>
- <span data-ttu-id="f5061-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="f5061-127">"\beta"</span></span>
- <span data-ttu-id="f5061-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="f5061-128">"\gamma"</span></span>
- <span data-ttu-id="f5061-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="f5061-129">"\delta"</span></span>
- <span data-ttu-id="f5061-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="f5061-130">"\omega"</span></span>
- <span data-ttu-id="f5061-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="f5061-131">"\bra"</span></span>
- <span data-ttu-id="f5061-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="f5061-132">"\ket"</span></span>
- <span data-ttu-id="f5061-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="f5061-133">"\boldone"</span></span>
- <span data-ttu-id="f5061-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="f5061-134">"\\\\"</span></span>
- <span data-ttu-id="f5061-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="f5061-135">"\\"</span></span>
- <span data-ttu-id="f5061-136">"="</span><span class="sxs-lookup"><span data-stu-id="f5061-136">"="</span></span>
- <span data-ttu-id="f5061-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="f5061-137">"\frac"</span></span>
- <span data-ttu-id="f5061-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="f5061-138">"\text"</span></span>
- <span data-ttu-id="f5061-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="f5061-139">"\mapsto"</span></span>
- <span data-ttu-id="f5061-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="f5061-140">"\dagger"</span></span>
- <span data-ttu-id="f5061-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="f5061-141">"\to"</span></span>
- <span data-ttu-id="f5061-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="f5061-142">"\begin{cases}"</span></span>
- <span data-ttu-id="f5061-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="f5061-143">"\end{cases}"</span></span>
- <span data-ttu-id="f5061-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="f5061-144">"\operatorname"</span></span>
- <span data-ttu-id="f5061-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="f5061-145">"\braket"</span></span>
- <span data-ttu-id="f5061-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="f5061-146">"\id"</span></span>
- <span data-ttu-id="f5061-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="f5061-147">"\expect"</span></span>
- <span data-ttu-id="f5061-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="f5061-148">"\defeq"</span></span>
- <span data-ttu-id="f5061-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="f5061-149">"\variance"</span></span>
- <span data-ttu-id="f5061-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="f5061-150">"\dd"</span></span>
- <span data-ttu-id="f5061-151">"&"</span><span class="sxs-lookup"><span data-stu-id="f5061-151">"&"</span></span>
- <span data-ttu-id="f5061-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="f5061-152">"\begin{align}"</span></span>
- <span data-ttu-id="f5061-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="f5061-153">"\end{align}"</span></span>
- <span data-ttu-id="f5061-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="f5061-154">"\Lambda"</span></span>
- <span data-ttu-id="f5061-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="f5061-155">"\lambda"</span></span>
- <span data-ttu-id="f5061-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="f5061-156">"\Omega"</span></span>
- <span data-ttu-id="f5061-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="f5061-157">"\mathrm"</span></span>
- <span data-ttu-id="f5061-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="f5061-158">"\left"</span></span>
- <span data-ttu-id="f5061-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="f5061-159">"\right"</span></span>
- <span data-ttu-id="f5061-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="f5061-160">"\qquad"</span></span>
- <span data-ttu-id="f5061-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="f5061-161">"\times"</span></span>
- <span data-ttu-id="f5061-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="f5061-162">"\big"</span></span>
- <span data-ttu-id="f5061-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="f5061-163">"\langle"</span></span>
- <span data-ttu-id="f5061-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="f5061-164">"\rangle"</span></span>
- <span data-ttu-id="f5061-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="f5061-165">"\bigg"</span></span>
- <span data-ttu-id="f5061-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="f5061-166">"\Big"</span></span>
- <span data-ttu-id="f5061-167">"|"</span><span class="sxs-lookup"><span data-stu-id="f5061-167">"|"</span></span>
- <span data-ttu-id="f5061-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="f5061-168">"\mathbb"</span></span>
- <span data-ttu-id="f5061-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="f5061-169">"\vec"</span></span>
- <span data-ttu-id="f5061-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="f5061-170">"\in"</span></span>
- <span data-ttu-id="f5061-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="f5061-171">"\texttt"</span></span>
- <span data-ttu-id="f5061-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="f5061-172">"\ne"</span></span>
- <span data-ttu-id="f5061-173">"<"</span><span class="sxs-lookup"><span data-stu-id="f5061-173">"<"</span></span>
- <span data-ttu-id="f5061-174">">"</span><span class="sxs-lookup"><span data-stu-id="f5061-174">">"</span></span>
- <span data-ttu-id="f5061-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="f5061-175">"\leq"</span></span>
- <span data-ttu-id="f5061-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="f5061-176">"\geq"</span></span>
- <span data-ttu-id="f5061-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="f5061-177">"~~"</span></span>
- <span data-ttu-id="f5061-178">"~"</span><span class="sxs-lookup"><span data-stu-id="f5061-178">"~"</span></span>
- <span data-ttu-id="f5061-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="f5061-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="f5061-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="f5061-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="f5061-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="f5061-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="f5061-182">Quantum Oracle</span><span class="sxs-lookup"><span data-stu-id="f5061-182">Quantum Oracles</span></span>

<span data-ttu-id="f5061-183">En Oracle $ O $ är en "svart box"-åtgärd som används som inmatad till en annan algoritm.</span><span class="sxs-lookup"><span data-stu-id="f5061-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="f5061-184">Ofta definieras sådana åtgärder med hjälp av en klassisk funktion $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ som tar en $ n $ -bitars binär indata och producerar en $ m $ -bitars binär utdata.</span><span class="sxs-lookup"><span data-stu-id="f5061-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="f5061-185">Det gör du genom att tänka på ett visst binärt $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="f5061-186">Vi kan märka qubit tillstånd som $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="f5061-187">Vi kan först försöka definiera $ o $ så att $ o \ket { x } = \ket { f (x) } $ , men det har ett par problem.</span><span class="sxs-lookup"><span data-stu-id="f5061-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="f5061-188">För $ det första $ kan f ha olika storlekar på indata och utdata ( $ n \ne m $ ), som att tillämpa $ O $ skulle ändra antalet qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="f5061-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="f5061-189">Andra, även om $ n = m $ , kanske funktionen inte är inverteras: om $ f (x) = f (y) $ för vissa $ x \ne y $ , så $ o \ket { x } = o y, \ket { } $ men $ o ^ o \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="f5061-190">Det innebär att vi inte kan skapa den angränsande åtgärden $ O ^ \dagger $ , och Oracle måste ha ett angränsande definierat för dem.</span><span class="sxs-lookup"><span data-stu-id="f5061-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="f5061-191">Definiera en Oracle genom att påverka beräknings bas staterna</span><span class="sxs-lookup"><span data-stu-id="f5061-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="f5061-192">Vi kan hantera båda dessa problem genom att introducera ett andra register av $ m $ qubits för att hålla vårt svar.</span><span class="sxs-lookup"><span data-stu-id="f5061-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="f5061-193">Därefter definierar vi resultatet av Oracle i alla beräknings grund lägen: för alla $ x \in \\ { 0, 1 \\ } ^ n $ och $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="f5061-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="f5061-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="f5061-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="f5061-195">Nu $ = \dagger $ måste vi ha löst båda de tidigare problemen.</span><span class="sxs-lookup"><span data-stu-id="f5061-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="f5061-196">>Om du vill se att o $ = { \dagger } $ $ ^ 2 = \boldone $ sedan $ \oplus b \oplus b = a $ för alla $ a, b \in \: :: No-Loc ({)::: 0, 1 \: :: No-Loc (}): $ ::.</span><span class="sxs-lookup"><span data-stu-id="f5061-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="f5061-197">>Det innebär att $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="f5061-198">Det är viktigt att definiera en Oracle på det här sättet för varje beräknings bas status $ \ket { x } \ket { y } $ definierar också hur $ O $ fungerar för alla andra tillstånd.</span><span class="sxs-lookup"><span data-stu-id="f5061-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="f5061-199">Detta följer omedelbart från det faktum att $ O $ , precis som alla Quantum-åtgärder, är linjärt i det tillstånd som det fungerar på.</span><span class="sxs-lookup"><span data-stu-id="f5061-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="f5061-200">Överväg Hadamard-åtgärden, till exempel, som definieras av $ h \ket { 0 } = \ket { + } $ och $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="f5061-201">Om vi vill veta hur $ h $ agerar på $ \ket { + } $ kan vi använda den här $ H $ är linjär,</span><span class="sxs-lookup"><span data-stu-id="f5061-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="f5061-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="f5061-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="f5061-203">&= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="f5061-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="f5061-204">Om du definierar vår Oracle $ O $ kan vi på samma sätt använda att alla tillstånd $ \ket { \psi } $ på $ n + m $ qubits kan skrivas som</span><span class="sxs-lookup"><span data-stu-id="f5061-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="f5061-205">\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="f5061-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="f5061-206">där $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ representerar koefficienterna för status $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="f5061-207">Därför</span><span class="sxs-lookup"><span data-stu-id="f5061-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="f5061-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="f5061-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="f5061-209">&= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="f5061-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="f5061-210">Fas Oracle</span><span class="sxs-lookup"><span data-stu-id="f5061-210">Phase oracles</span></span>
<span data-ttu-id="f5061-211">Alternativt kan vi koda $ f $ till en Oracle- $ O $ genom att använda en _fas_ baserat på inmatat på $ O $ . Vi kan till exempel definiera $ O $ så att $$</span><span class="sxs-lookup"><span data-stu-id="f5061-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="f5061-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="f5061-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="f5061-213">Om en fas Oracle agerar i ett register inlednings vis i ett beräknings underlags tillstånd $ \ket { x } $ , är den här fasen en global fas och går därför inte att observera.</span><span class="sxs-lookup"><span data-stu-id="f5061-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="f5061-214">Men en sådan Oracle kan vara en mycket kraftfull resurs om den tillämpas på en överposition eller som en kontrollerad åtgärd.</span><span class="sxs-lookup"><span data-stu-id="f5061-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="f5061-215">Anta till exempel en fas Oracle- $ O_f $ för en qubit funktion $ f $ .</span><span class="sxs-lookup"><span data-stu-id="f5061-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="f5061-216">Dra $$</span><span class="sxs-lookup"><span data-stu-id="f5061-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="f5061-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="f5061-217">O_f \ket{+}</span></span>
        <span data-ttu-id="f5061-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="f5061-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="f5061-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="f5061-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="f5061-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="f5061-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="f5061-221">&=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="f5061-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="f5061-222">I allmänhet kan båda vyerna i Oracle utökas för att representera klassiska funktioner som returnerar reella tal i stället för bara en enda bit.</span><span class="sxs-lookup"><span data-stu-id="f5061-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="f5061-223">Att välja det bästa sättet att implementera en Oracle är beroende av hur den här Oracle kommer att användas inom en specifik algoritm.</span><span class="sxs-lookup"><span data-stu-id="f5061-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="f5061-224">Till exempel är [Deutsch-Jozsa-algoritmen](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) beroende av den Oracle som implementerats på det första sättet, medan [algoritmen för Grover är](https://en.wikipedia.org/wiki/Grover's_algorithm) beroende av den Oracle som implementerats på det andra sättet.</span><span class="sxs-lookup"><span data-stu-id="f5061-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="f5061-225">För mer information, föreslår vi diskussionen i [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="f5061-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
