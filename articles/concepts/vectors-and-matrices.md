---
<span data-ttu-id="cd5d6-101">rubrik: vektorer och matriser i Beskrivning av Quantum Computing: Lär dig grunderna för hur du arbetar med vektorer och matriser.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="cd5d6-102">författare: QuantumWriter UID: Microsoft. Quantum. Concepts. Vectors MS. author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: artikeln No-Loc:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="cd5d6-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-103">"Q#"</span></span>
- <span data-ttu-id="cd5d6-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-104">"$$v"</span></span>
- <span data-ttu-id="cd5d6-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-105">"$$"</span></span>
- <span data-ttu-id="cd5d6-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-106">"$$"</span></span>
- <span data-ttu-id="cd5d6-107">"$"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-107">"$"</span></span>
- <span data-ttu-id="cd5d6-108">"$"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-108">"$"</span></span>
- <span data-ttu-id="cd5d6-109">"$"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-109">"$"</span></span>
- <span data-ttu-id="cd5d6-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-110">"$$"</span></span>
- <span data-ttu-id="cd5d6-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-111">"\cdots"</span></span>
- <span data-ttu-id="cd5d6-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-112">"bmatrix"</span></span>
- <span data-ttu-id="cd5d6-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-113">"\ddots"</span></span>
- <span data-ttu-id="cd5d6-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-114">"\equiv"</span></span>
- <span data-ttu-id="cd5d6-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-115">"\sum"</span></span>
- <span data-ttu-id="cd5d6-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-116">"\begin"</span></span>
- <span data-ttu-id="cd5d6-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-117">"\end"</span></span>
- <span data-ttu-id="cd5d6-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-118">"\sqrt"</span></span>
- <span data-ttu-id="cd5d6-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-119">"\otimes"</span></span>
- <span data-ttu-id="cd5d6-120">"{"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-120">"{"</span></span>
- <span data-ttu-id="cd5d6-121">"}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-121">"}"</span></span>
- <span data-ttu-id="cd5d6-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-122">"\text"</span></span>
- <span data-ttu-id="cd5d6-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-123">"\phi"</span></span>
- <span data-ttu-id="cd5d6-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-124">"\kappa"</span></span>
- <span data-ttu-id="cd5d6-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-125">"\psi"</span></span>
- <span data-ttu-id="cd5d6-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-126">"\alpha"</span></span>
- <span data-ttu-id="cd5d6-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-127">"\beta"</span></span>
- <span data-ttu-id="cd5d6-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-128">"\gamma"</span></span>
- <span data-ttu-id="cd5d6-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-129">"\delta"</span></span>
- <span data-ttu-id="cd5d6-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-130">"\omega"</span></span>
- <span data-ttu-id="cd5d6-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-131">"\bra"</span></span>
- <span data-ttu-id="cd5d6-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-132">"\ket"</span></span>
- <span data-ttu-id="cd5d6-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-133">"\boldone"</span></span>
- <span data-ttu-id="cd5d6-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-134">"\\\\"</span></span>
- <span data-ttu-id="cd5d6-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-135">"\\"</span></span>
- <span data-ttu-id="cd5d6-136">"="</span><span class="sxs-lookup"><span data-stu-id="cd5d6-136">"="</span></span>
- <span data-ttu-id="cd5d6-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-137">"\frac"</span></span>
- <span data-ttu-id="cd5d6-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-138">"\text"</span></span>
- <span data-ttu-id="cd5d6-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-139">"\mapsto"</span></span>
- <span data-ttu-id="cd5d6-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-140">"\dagger"</span></span>
- <span data-ttu-id="cd5d6-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-141">"\to"</span></span>
- <span data-ttu-id="cd5d6-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-142">"\begin{cases}"</span></span>
- <span data-ttu-id="cd5d6-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-143">"\end{cases}"</span></span>
- <span data-ttu-id="cd5d6-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-144">"\operatorname"</span></span>
- <span data-ttu-id="cd5d6-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-145">"\braket"</span></span>
- <span data-ttu-id="cd5d6-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-146">"\id"</span></span>
- <span data-ttu-id="cd5d6-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-147">"\expect"</span></span>
- <span data-ttu-id="cd5d6-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-148">"\defeq"</span></span>
- <span data-ttu-id="cd5d6-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-149">"\variance"</span></span>
- <span data-ttu-id="cd5d6-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-150">"\dd"</span></span>
- <span data-ttu-id="cd5d6-151">"&"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-151">"&"</span></span>
- <span data-ttu-id="cd5d6-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-152">"\begin{align}"</span></span>
- <span data-ttu-id="cd5d6-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-153">"\end{align}"</span></span>
- <span data-ttu-id="cd5d6-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-154">"\Lambda"</span></span>
- <span data-ttu-id="cd5d6-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-155">"\lambda"</span></span>
- <span data-ttu-id="cd5d6-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-156">"\Omega"</span></span>
- <span data-ttu-id="cd5d6-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-157">"\mathrm"</span></span>
- <span data-ttu-id="cd5d6-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-158">"\left"</span></span>
- <span data-ttu-id="cd5d6-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-159">"\right"</span></span>
- <span data-ttu-id="cd5d6-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-160">"\qquad"</span></span>
- <span data-ttu-id="cd5d6-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-161">"\times"</span></span>
- <span data-ttu-id="cd5d6-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-162">"\big"</span></span>
- <span data-ttu-id="cd5d6-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-163">"\langle"</span></span>
- <span data-ttu-id="cd5d6-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-164">"\rangle"</span></span>
- <span data-ttu-id="cd5d6-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-165">"\bigg"</span></span>
- <span data-ttu-id="cd5d6-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-166">"\Big"</span></span>
- <span data-ttu-id="cd5d6-167">"|"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-167">"|"</span></span>
- <span data-ttu-id="cd5d6-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-168">"\mathbb"</span></span>
- <span data-ttu-id="cd5d6-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-169">"\vec"</span></span>
- <span data-ttu-id="cd5d6-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-170">"\in"</span></span>
- <span data-ttu-id="cd5d6-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-171">"\texttt"</span></span>
- <span data-ttu-id="cd5d6-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-172">"\ne"</span></span>
- <span data-ttu-id="cd5d6-173">"<"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-173">"<"</span></span>
- <span data-ttu-id="cd5d6-174">">"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-174">">"</span></span>
- <span data-ttu-id="cd5d6-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-175">"\leq"</span></span>
- <span data-ttu-id="cd5d6-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-176">"\geq"</span></span>
- <span data-ttu-id="cd5d6-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-177">"~~"</span></span>
- <span data-ttu-id="cd5d6-178">"~"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-178">"~"</span></span>
- <span data-ttu-id="cd5d6-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="cd5d6-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="cd5d6-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="cd5d6-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="cd5d6-182">Vektorer och matriser</span><span class="sxs-lookup"><span data-stu-id="cd5d6-182">Vectors and Matrices</span></span>

<span data-ttu-id="cd5d6-183">En del bekant med vektorer och matriser är viktigt för att förstå Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="cd5d6-184">Vi ger en kort introduktion nedan och intresserade läsare rekommenderas att läsa en standard referens för linjära algebra, till exempel *Strang, G. (1993). Introduktion till linjär algebra (vol. 3). Wellesley, MA: Wellesley-Cambridge press* eller a online Reference, till exempel [linjär algebra](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="cd5d6-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="cd5d6-185">En kolumn vektor (eller bara [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ av dimension (eller storlek) $ n $ är en samling med $ n $ komplexa tal $ (v_1, v_2, \ldots, V_n) $ ordnade som en kolumn:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="cd5d6-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="cd5d6-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-187">v_1\\\\</span></span>
<span data-ttu-id="cd5d6-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-188">v_2\\\\</span></span>
<span data-ttu-id="cd5d6-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-189">\vdots\\\\</span></span>
<span data-ttu-id="cd5d6-190">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="cd5d6-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="cd5d6-191">Normen för en Vector $ v $ definieras som $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="cd5d6-192">En Vector anses vara av enhets norm (eller också kallas den för en [*enhets vektor*](https://en.wikipedia.org/wiki/Unit_vector)) om dess norm är $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="cd5d6-193">Det [*angränsande av en Vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ har $ tilldelats v ^ \dagger $ och definieras som följande rad vektor där $ \* $ anger det komplexa konjugatet.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="cd5d6-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & V_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="cd5d6-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="cd5d6-195">Det vanligaste sättet att multiplicera två vektorer är genom den [*inre produkten*](https://en.wikipedia.org/wiki/Inner_product_space), även kallat en punkt produkt.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="cd5d6-196">Den inre produkten ger projektionen av en Vector till en annan och är värdefull för att beskriva hur man uttrycker en Vector som en summa av andra enklare vektorer.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="cd5d6-197">Den inre produkten mellan $ u $ och $ v $ , detecknad $ \left \langle u, v \right \rangle $ definieras som</span><span class="sxs-lookup"><span data-stu-id="cd5d6-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="cd5d6-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="cd5d6-199">Den här notationen tillåter också att en Vector $ v $ -volym skrivs som $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="cd5d6-200">Vi kan multiplicera en Vector med ett nummer $ c $ för att skapa en ny Vector vars poster multipliceras med $ c $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="cd5d6-201">Vi kan också lägga till två vektorer $ u $ och $ v $ för att skapa en ny Vector vars poster är summan av posterna för $ u $ och $ v $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="cd5d6-202">Dessa åtgärder beskrivs nedan:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-202">These operations are depicted below:</span></span>

<span data-ttu-id="cd5d6-203">$$\mathrm{Om } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="cd5d6-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-204">u_1\\\\</span></span>
<span data-ttu-id="cd5d6-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-205">u_2\\\\</span></span>
<span data-ttu-id="cd5d6-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-206">\vdots\\\\</span></span>
<span data-ttu-id="cd5d6-207">u_n \end{bmatrix} ~ \mathrm { och}~</span><span class="sxs-lookup"><span data-stu-id="cd5d6-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="cd5d6-208">lodrät=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-209">v_1\\\\</span></span>
    <span data-ttu-id="cd5d6-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-210">v_2\\\\</span></span>
    <span data-ttu-id="cd5d6-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-211">\vdots\\\\</span></span>
    <span data-ttu-id="cd5d6-212">V_n \end{bmatrix} och ~ \mathrm { sedan}~</span><span class="sxs-lookup"><span data-stu-id="cd5d6-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="cd5d6-213">Au + BV=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="cd5d6-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="cd5d6-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="cd5d6-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-216">\vdots\\\\</span></span>
<span data-ttu-id="cd5d6-217">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="cd5d6-218">En [*matris*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) med storleken $ m \times n $ är en samling med $ mn- $ komplexa tal ordnade i $ m- $ rader och $ n $ kolumner som visas nedan:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="cd5d6-219">$$Avstånd=</span><span class="sxs-lookup"><span data-stu-id="cd5d6-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="cd5d6-220">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="cd5d6-221">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="cd5d6-222">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="cd5d6-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="cd5d6-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="cd5d6-224">Observera att en Vector med dimension $ n $ bara är en matris med storleken $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="cd5d6-225">Precis som med vektorer kan vi multiplicera en matris med ett nummer $ c $ för att hämta en ny matris där varje post multipliceras med $ c $ , och vi kan lägga till två matriser av samma storlek för att skapa en ny matris vars poster är summan av respektive poster för de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="cd5d6-226">Matris-och beskrivares produkter</span><span class="sxs-lookup"><span data-stu-id="cd5d6-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="cd5d6-227">Vi kan också multiplicera två matriser $ m $ i dimension $ m \times n $ och $ n $ i dimension $ n \times p $ för att få en ny matris $ p $ av dimension $ m \times p $ enligt följande:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="cd5d6-228">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="cd5d6-229">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="cd5d6-230">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="cd5d6-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="cd5d6-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="cd5d6-233">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="cd5d6-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="cd5d6-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="cd5d6-236">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="cd5d6-237">om posterna i $ P $ är $ P_ { IK } = \sum _j M_för { } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="cd5d6-238">Posten $ P_ 11 är till exempel { } $ den inre produkten av den första raden i $ M $ med den första kolumnen i $ N $ . Observera att eftersom en Vector bara är ett specialfall av en matris, sträcker sig denna definition till multiplikation med mat ris vektorer.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="cd5d6-239">Alla matriser vi anser är antingen fyrkantiga matriser, där antalet rader och kolumner är lika med, eller vektorer, som motsvarar endast $ 1 $ kolumn.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="cd5d6-240">En speciell klammer är [*identitets mat*](https://en.wikipedia.org/wiki/Identity_matrix)ris, $ \boldone $ som har alla dess diagonala element lika med $ 1 $ och återstående element som är lika med $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="cd5d6-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="cd5d6-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="cd5d6-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="cd5d6-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="cd5d6-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="cd5d6-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="cd5d6-245">För en fyrkantig matris $ a $ säger vi att en matris $ B $ är [*inversen*](https://en.wikipedia.org/wiki/Invertible_matrix) om $ AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="cd5d6-246">Inversen till en matris behöver inte finnas, men när den finns är den unik och vi anger den som $ en ^ { -1 } $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="cd5d6-247">För alla matriser $ m $ är det angränsande eller konjugatet som transponeras till $ M $ en matris $ N $ som $ N_ { } = { Ji: s M_ } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="cd5d6-248">Det angränsande av $ m $ är vanligt vis betecknat $ m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="cd5d6-249">Vi säger att en matris U är av sin egen $ $ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) om $ UU ^ \dagger = u ^ \dagger u = \boldone $ eller motsvarande, $ u ^ { -1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="cd5d6-250">Kanske är den viktigaste egenskapen för enhetliga matriser att de behåller normen i en Vector.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="cd5d6-251">Detta inträffar eftersom</span><span class="sxs-lookup"><span data-stu-id="cd5d6-251">This happens because</span></span> 

<span data-ttu-id="cd5d6-252">$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v, u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="cd5d6-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="cd5d6-253">En matris $ m $ sa att vara [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) om $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="cd5d6-254">Slutligen är bevarans [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (eller Kronecker produkt) av två matriser $ m $ med storleken $ m \times n $ och $ n $ av storlek $ p \times q $ en större matris $ p = m \otimes n $ av storlek $ MP \times NQ $ och hämtas från $ M $ och $ n $ enligt följande:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="cd5d6-255">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="cd5d6-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-256">M_ { 11 } ~~ \cdots ~~ M_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="cd5d6-257">M_ { M1 } ~~ \cdots ~~ M_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="cd5d6-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-258">N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="cd5d6-259">N_ { P1 } ~~ \cdots ~~ N_ { PQ}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="cd5d6-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="cd5d6-261">M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="cd5d6-262">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="cd5d6-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="cd5d6-263">M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="cd5d6-265">Detta demonstreras bättre med några exempel:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="cd5d6-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-267">a \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="cd5d6-268">\\\\[1,5 EM] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="cd5d6-269">=\begin{bmatrix}a c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="cd5d6-270">och</span><span class="sxs-lookup"><span data-stu-id="cd5d6-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-271">a \ b \\\\ c \ d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="cd5d6-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="cd5d6-273">en\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-275">t\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-279">styr\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="cd5d6-280">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="cd5d6-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="cd5d6-281">AE \ AF \ BF\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="cd5d6-282">AG \ Ah \ BG \ BH\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="cd5d6-283">CE \ CF \ de \ DF\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="cd5d6-284">CG \ CH \ GD \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="cd5d6-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="cd5d6-285">En slutgiltig, användbar, utgångs konvention som omger betecknings produkter är att, för alla vektorer $ v $ eller Matrix $ m $ , $ v ^ { \otimes n } $ eller $ M ^ { \otimes n, } $ är kort hand för en $ n $ -viknings produkt med upprepade Skriv sätt.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="cd5d6-286">Exempel:</span><span class="sxs-lookup"><span data-stu-id="cd5d6-286">For example:</span></span>

\begin{align}
<span data-ttu-id="cd5d6-287">&\begin{bmatrix}1 \\\\ 0 1 1 0, 1 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \end{bmatrix} \qquad \begin{bmatrix} \\\\ \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 1-1 } = \begin{bmatrix} \\\\ – 1 \\\\ \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="cd5d6-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="cd5d6-288">&\begin{bmatrix}0 & 1 1 0 1 0 \\\\ & \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & , \\\\ 0 & \end{bmatrix} \qquad \begin{bmatrix} & 1 \\\\ 1 0 & \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 1 0 0 1 0 0 1 0 0.</span><span class="sxs-lookup"><span data-stu-id="cd5d6-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
