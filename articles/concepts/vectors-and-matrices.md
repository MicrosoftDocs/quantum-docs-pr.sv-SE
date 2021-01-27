---
<span data-ttu-id="20dc0-101">rubrik: vektorer och matriser i Beskrivning av Quantum Computing: Lär dig grunderna för hur du arbetar med vektorer och matriser.</span><span class="sxs-lookup"><span data-stu-id="20dc0-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="20dc0-102">författare: QuantumWriter-UID: Microsoft. Quantum. Concepts. Vectors MS. author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuell No-Loc:</span><span class="sxs-lookup"><span data-stu-id="20dc0-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="20dc0-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="20dc0-103">"Q#"</span></span>
- <span data-ttu-id="20dc0-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="20dc0-104">"$$v"</span></span>
- <span data-ttu-id="20dc0-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="20dc0-105">"$$"</span></span>
- <span data-ttu-id="20dc0-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="20dc0-106">"$$"</span></span>
- <span data-ttu-id="20dc0-107">"$"</span><span class="sxs-lookup"><span data-stu-id="20dc0-107">"$"</span></span>
- <span data-ttu-id="20dc0-108">"$"</span><span class="sxs-lookup"><span data-stu-id="20dc0-108">"$"</span></span>
- <span data-ttu-id="20dc0-109">"$"</span><span class="sxs-lookup"><span data-stu-id="20dc0-109">"$"</span></span>
- <span data-ttu-id="20dc0-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="20dc0-110">"$$"</span></span>
- <span data-ttu-id="20dc0-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="20dc0-111">"\cdots"</span></span>
- <span data-ttu-id="20dc0-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="20dc0-112">"bmatrix"</span></span>
- <span data-ttu-id="20dc0-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="20dc0-113">"\ddots"</span></span>
- <span data-ttu-id="20dc0-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="20dc0-114">"\equiv"</span></span>
- <span data-ttu-id="20dc0-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="20dc0-115">"\sum"</span></span>
- <span data-ttu-id="20dc0-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="20dc0-116">"\begin"</span></span>
- <span data-ttu-id="20dc0-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="20dc0-117">"\end"</span></span>
- <span data-ttu-id="20dc0-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="20dc0-118">"\sqrt"</span></span>
- <span data-ttu-id="20dc0-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="20dc0-119">"\otimes"</span></span>
- <span data-ttu-id="20dc0-120">"{"</span><span class="sxs-lookup"><span data-stu-id="20dc0-120">"{"</span></span>
- <span data-ttu-id="20dc0-121">"}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-121">"}"</span></span>
- <span data-ttu-id="20dc0-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="20dc0-122">"\text"</span></span>
- <span data-ttu-id="20dc0-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="20dc0-123">"\phi"</span></span>
- <span data-ttu-id="20dc0-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="20dc0-124">"\kappa"</span></span>
- <span data-ttu-id="20dc0-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="20dc0-125">"\psi"</span></span>
- <span data-ttu-id="20dc0-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="20dc0-126">"\alpha"</span></span>
- <span data-ttu-id="20dc0-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="20dc0-127">"\beta"</span></span>
- <span data-ttu-id="20dc0-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="20dc0-128">"\gamma"</span></span>
- <span data-ttu-id="20dc0-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="20dc0-129">"\delta"</span></span>
- <span data-ttu-id="20dc0-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="20dc0-130">"\omega"</span></span>
- <span data-ttu-id="20dc0-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="20dc0-131">"\bra"</span></span>
- <span data-ttu-id="20dc0-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="20dc0-132">"\ket"</span></span>
- <span data-ttu-id="20dc0-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="20dc0-133">"\boldone"</span></span>
- <span data-ttu-id="20dc0-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="20dc0-134">"\\\\"</span></span>
- <span data-ttu-id="20dc0-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="20dc0-135">"\\"</span></span>
- <span data-ttu-id="20dc0-136">"="</span><span class="sxs-lookup"><span data-stu-id="20dc0-136">"="</span></span>
- <span data-ttu-id="20dc0-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="20dc0-137">"\frac"</span></span>
- <span data-ttu-id="20dc0-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="20dc0-138">"\text"</span></span>
- <span data-ttu-id="20dc0-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="20dc0-139">"\mapsto"</span></span>
- <span data-ttu-id="20dc0-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="20dc0-140">"\dagger"</span></span>
- <span data-ttu-id="20dc0-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="20dc0-141">"\to"</span></span>
- <span data-ttu-id="20dc0-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-142">"\begin{cases}"</span></span>
- <span data-ttu-id="20dc0-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-143">"\end{cases}"</span></span>
- <span data-ttu-id="20dc0-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="20dc0-144">"\operatorname"</span></span>
- <span data-ttu-id="20dc0-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="20dc0-145">"\braket"</span></span>
- <span data-ttu-id="20dc0-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="20dc0-146">"\id"</span></span>
- <span data-ttu-id="20dc0-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="20dc0-147">"\expect"</span></span>
- <span data-ttu-id="20dc0-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="20dc0-148">"\defeq"</span></span>
- <span data-ttu-id="20dc0-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="20dc0-149">"\variance"</span></span>
- <span data-ttu-id="20dc0-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="20dc0-150">"\dd"</span></span>
- <span data-ttu-id="20dc0-151">"&"</span><span class="sxs-lookup"><span data-stu-id="20dc0-151">"&"</span></span>
- <span data-ttu-id="20dc0-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-152">"\begin{align}"</span></span>
- <span data-ttu-id="20dc0-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-153">"\end{align}"</span></span>
- <span data-ttu-id="20dc0-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="20dc0-154">"\Lambda"</span></span>
- <span data-ttu-id="20dc0-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="20dc0-155">"\lambda"</span></span>
- <span data-ttu-id="20dc0-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="20dc0-156">"\Omega"</span></span>
- <span data-ttu-id="20dc0-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="20dc0-157">"\mathrm"</span></span>
- <span data-ttu-id="20dc0-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="20dc0-158">"\left"</span></span>
- <span data-ttu-id="20dc0-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="20dc0-159">"\right"</span></span>
- <span data-ttu-id="20dc0-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="20dc0-160">"\qquad"</span></span>
- <span data-ttu-id="20dc0-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="20dc0-161">"\times"</span></span>
- <span data-ttu-id="20dc0-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="20dc0-162">"\big"</span></span>
- <span data-ttu-id="20dc0-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="20dc0-163">"\langle"</span></span>
- <span data-ttu-id="20dc0-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="20dc0-164">"\rangle"</span></span>
- <span data-ttu-id="20dc0-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="20dc0-165">"\bigg"</span></span>
- <span data-ttu-id="20dc0-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="20dc0-166">"\Big"</span></span>
- <span data-ttu-id="20dc0-167">"|"</span><span class="sxs-lookup"><span data-stu-id="20dc0-167">"|"</span></span>
- <span data-ttu-id="20dc0-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="20dc0-168">"\mathbb"</span></span>
- <span data-ttu-id="20dc0-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="20dc0-169">"\vec"</span></span>
- <span data-ttu-id="20dc0-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="20dc0-170">"\in"</span></span>
- <span data-ttu-id="20dc0-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="20dc0-171">"\texttt"</span></span>
- <span data-ttu-id="20dc0-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="20dc0-172">"\ne"</span></span>
- <span data-ttu-id="20dc0-173">"<"</span><span class="sxs-lookup"><span data-stu-id="20dc0-173">"<"</span></span>
- <span data-ttu-id="20dc0-174">">"</span><span class="sxs-lookup"><span data-stu-id="20dc0-174">">"</span></span>
- <span data-ttu-id="20dc0-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="20dc0-175">"\leq"</span></span>
- <span data-ttu-id="20dc0-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="20dc0-176">"\geq"</span></span>
- <span data-ttu-id="20dc0-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="20dc0-177">"~~"</span></span>
- <span data-ttu-id="20dc0-178">"~"</span><span class="sxs-lookup"><span data-stu-id="20dc0-178">"~"</span></span>
- <span data-ttu-id="20dc0-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="20dc0-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="20dc0-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="20dc0-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="20dc0-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="20dc0-182">Vektorer och matriser</span><span class="sxs-lookup"><span data-stu-id="20dc0-182">Vectors and Matrices</span></span>

<span data-ttu-id="20dc0-183">En del bekant med vektorer och matriser är viktigt för att förstå Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="20dc0-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="20dc0-184">Vi ger en kort introduktion nedan och intresserade läsare rekommenderas att läsa en standard referens för linjära algebra, till exempel *Strang, G. (1993). Introduktion till linjär algebra (vol. 3). Wellesley, MA: Wellesley-Cambridge tryck* eller en online-referens, till exempel [linjär algebra](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="20dc0-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="20dc0-185">En kolumn vektor (eller bara [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ av dimension (eller storlek) $ n $ är en samling med $ n $ komplexa tal $ (v_1, v_2, \ldots, V_n) $ ordnade som en kolumn:</span><span class="sxs-lookup"><span data-stu-id="20dc0-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="20dc0-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="20dc0-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-187">v_1\\\\</span></span>
<span data-ttu-id="20dc0-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-188">v_2\\\\</span></span>
<span data-ttu-id="20dc0-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-189">\vdots\\\\</span></span>
<span data-ttu-id="20dc0-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="20dc0-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="20dc0-191">Normen för en Vector $ v $ definieras som $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="20dc0-192">En Vector anses vara av enhets norm (eller också kallas den för en [*enhets vektor*](https://en.wikipedia.org/wiki/Unit_vector)) om dess norm är $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="20dc0-193">Det [*angränsande av en Vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ har $ tilldelats v ^ \dagger $ och definieras som följande rad vektor där $ \* $ anger det komplexa konjugatet.</span><span class="sxs-lookup"><span data-stu-id="20dc0-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="20dc0-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & V_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="20dc0-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="20dc0-195">Det vanligaste sättet att multiplicera två vektorer är genom den [*inre produkten*](https://en.wikipedia.org/wiki/Inner_product_space), även kallat en punkt produkt.</span><span class="sxs-lookup"><span data-stu-id="20dc0-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="20dc0-196">Den inre produkten ger projektionen av en Vector till en annan och är värdefull för att beskriva hur man uttrycker en Vector som en summa av andra enklare vektorer.</span><span class="sxs-lookup"><span data-stu-id="20dc0-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="20dc0-197">Den inre produkten mellan $ u $ och $ v $ , detecknad $ \left \langle u, v \right \rangle $ definieras som</span><span class="sxs-lookup"><span data-stu-id="20dc0-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="20dc0-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="20dc0-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="20dc0-199">Den här notationen tillåter också att en Vector $ v $ -volym skrivs som $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="20dc0-200">Vi kan multiplicera en Vector med ett nummer $ c $ för att skapa en ny Vector vars poster multipliceras med $ c $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="20dc0-201">Vi kan också lägga till två vektorer $ u $ och $ v $ för att skapa en ny Vector vars poster är summan av posterna för $ u $ och $ v $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="20dc0-202">Dessa åtgärder beskrivs nedan:</span><span class="sxs-lookup"><span data-stu-id="20dc0-202">These operations are depicted below:</span></span>

<span data-ttu-id="20dc0-203">$$\mathrm{Om } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="20dc0-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-204">u_1\\\\</span></span>
<span data-ttu-id="20dc0-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-205">u_2\\\\</span></span>
<span data-ttu-id="20dc0-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-206">\vdots\\\\</span></span>
<span data-ttu-id="20dc0-207">u_n \end{bmatrix} ~ \mathrm { och}~</span><span class="sxs-lookup"><span data-stu-id="20dc0-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="20dc0-208">lodrät =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="20dc0-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-209">v_1\\\\</span></span>
    <span data-ttu-id="20dc0-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-210">v_2\\\\</span></span>
    <span data-ttu-id="20dc0-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-211">\vdots\\\\</span></span>
    <span data-ttu-id="20dc0-212">V_n \end{bmatrix} och ~ \mathrm { sedan}~</span><span class="sxs-lookup"><span data-stu-id="20dc0-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="20dc0-213">Au + BV =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="20dc0-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="20dc0-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="20dc0-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-216">\vdots\\\\</span></span>
<span data-ttu-id="20dc0-217">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="20dc0-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="20dc0-218">En [*matris*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) med storleken $ m \times n $ är en samling med $ mn- $ komplexa tal ordnade i $ m- $ rader och $ n $ kolumner som visas nedan:</span><span class="sxs-lookup"><span data-stu-id="20dc0-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="20dc0-219">$$Avstånd =</span><span class="sxs-lookup"><span data-stu-id="20dc0-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="20dc0-220">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="20dc0-221">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="20dc0-222">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="20dc0-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="20dc0-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="20dc0-224">Observera att en Vector med dimension $ n $ bara är en matris med storleken $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="20dc0-225">Precis som med vektorer kan vi multiplicera en matris med ett nummer $ c $ för att hämta en ny matris där varje post multipliceras med $ c $ , och vi kan lägga till två matriser av samma storlek för att skapa en ny matris vars poster är summan av respektive poster för de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="20dc0-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="20dc0-226">Matris-och beskrivares produkter</span><span class="sxs-lookup"><span data-stu-id="20dc0-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="20dc0-227">Vi kan också multiplicera två matriser $ m $ i dimension $ m \times n $ och $ n $ i dimension $ n \times p $ för att få en ny matris $ p $ av dimension $ m \times p $ enligt följande:</span><span class="sxs-lookup"><span data-stu-id="20dc0-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="20dc0-228">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="20dc0-229">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="20dc0-230">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}</span><span class="sxs-lookup"><span data-stu-id="20dc0-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="20dc0-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="20dc0-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="20dc0-233">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}</span><span class="sxs-lookup"><span data-stu-id="20dc0-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="20dc0-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="20dc0-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="20dc0-236">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}</span><span class="sxs-lookup"><span data-stu-id="20dc0-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="20dc0-237">om posterna i $ P $ är $ P_ { IK } = \sum _j M_ för { } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="20dc0-238">Posten $ P_ 11 är till exempel { } $ den inre produkten av den första raden i $ M $ med den första kolumnen i $ N $ . Observera att eftersom en Vector bara är ett specialfall av en matris, sträcker sig denna definition till multiplikation med mat ris vektorer.</span><span class="sxs-lookup"><span data-stu-id="20dc0-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="20dc0-239">Alla matriser vi anser är antingen fyrkantiga matriser, där antalet rader och kolumner är lika med, eller vektorer, som motsvarar endast $ 1 $ kolumn.</span><span class="sxs-lookup"><span data-stu-id="20dc0-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="20dc0-240">En speciell klammer är [*identitets mat*](https://en.wikipedia.org/wiki/Identity_matrix)ris, $ \boldone $ som har alla dess diagonala element lika med $ 1 $ och återstående element som är lika med $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="20dc0-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="20dc0-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="20dc0-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="20dc0-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="20dc0-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="20dc0-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="20dc0-245">För en fyrkantig matris $ a $ säger vi att en matris $ B $ är [*inversen*](https://en.wikipedia.org/wiki/Invertible_matrix) om $ AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="20dc0-246">Inversen till en matris behöver inte finnas, men när den finns är den unik och vi anger den som $ en ^ { -1 } $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="20dc0-247">För alla matriser $ m $ är det angränsande eller konjugatet som transponeras till $ M $ en matris $ N $ som $ N_ { } = { Ji: s M_ } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="20dc0-248">Det angränsande av $ m $ är vanligt vis betecknat $ m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="20dc0-249">Vi säger att en matris U är av sin egen $ $ [](https://en.wikipedia.org/wiki/Unitary_matrix) om $ UU ^ \dagger = u ^ \dagger u = \boldone $ eller motsvarande, $ u ^ { -1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="20dc0-250">Kanske är den viktigaste egenskapen för enhetliga matriser att de behåller normen i en Vector.</span><span class="sxs-lookup"><span data-stu-id="20dc0-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="20dc0-251">Detta inträffar eftersom</span><span class="sxs-lookup"><span data-stu-id="20dc0-251">This happens because</span></span> 

<span data-ttu-id="20dc0-252">$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v, u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="20dc0-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="20dc0-253">En matris $ m $ sa att vara [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) om $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="20dc0-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="20dc0-254">Slutligen är bevarans [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (eller Kronecker produkt) av två matriser $ m $ med storleken $ m \times n $ och $ n $ av storlek $ p \times q $ en större matris $ p = m \otimes n $ av storlek $ MP \times NQ $ och hämtas från $ M $ och $ n $ enligt följande:</span><span class="sxs-lookup"><span data-stu-id="20dc0-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="20dc0-255">M \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="20dc0-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="20dc0-256">M_ { 11 } ~~ \cdots ~~ M_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="20dc0-257">M_ { M1 } ~~ \cdots ~~ M_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="20dc0-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="20dc0-258">N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="20dc0-259">N_ { P1 } ~~ \cdots ~~ N_ { PQ}</span><span class="sxs-lookup"><span data-stu-id="20dc0-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="20dc0-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="20dc0-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="20dc0-261">M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="20dc0-262">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="20dc0-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="20dc0-263">M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="20dc0-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="20dc0-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="20dc0-265">Detta demonstreras bättre med några exempel:</span><span class="sxs-lookup"><span data-stu-id="20dc0-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="20dc0-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="20dc0-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="20dc0-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="20dc0-268">\\\\[1,5 EM] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="20dc0-269">=\begin{bmatrix}a c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="20dc0-270">och</span><span class="sxs-lookup"><span data-stu-id="20dc0-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="20dc0-271">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="20dc0-272">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="20dc0-273">en\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="20dc0-274">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20dc0-275">t\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="20dc0-276">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20dc0-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="20dc0-278">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="20dc0-279">styr\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="20dc0-280">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="20dc0-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="20dc0-281">AE \ AF \ BF \\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="20dc0-282">AG \ Ah \ BG \ BH \\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="20dc0-283">CE \ CF \ de \ DF \\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="20dc0-284">CG \ CH \ GD \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="20dc0-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="20dc0-285">En slutgiltig, användbar, utgångs konvention som omger betecknings produkter är att, för alla vektorer $ v $ eller Matrix $ m $ , $ v ^ { \otimes n } $ eller $ M ^ { \otimes n, } $ är kort hand för en $ n $ -viknings produkt med upprepade Skriv sätt.</span><span class="sxs-lookup"><span data-stu-id="20dc0-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="20dc0-286">Exempel:</span><span class="sxs-lookup"><span data-stu-id="20dc0-286">For example:</span></span>

\begin{align}
<span data-ttu-id="20dc0-287">&\begin{bmatrix}1 \\\\ 0 1 1 0, 1 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \end{bmatrix} \qquad \begin{bmatrix} \\\\ \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 1-1 } = \begin{bmatrix} \\\\ – 1 \\\\ \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="20dc0-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="20dc0-288">&\begin{bmatrix}0 & 1 1 0 1 0 \\\\ & \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & , \\\\ 0 & \end{bmatrix} \qquad \begin{bmatrix} & 1 \\\\ 1 0 & \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 1 0 0 1 0 0 1 0 0.</span><span class="sxs-lookup"><span data-stu-id="20dc0-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
