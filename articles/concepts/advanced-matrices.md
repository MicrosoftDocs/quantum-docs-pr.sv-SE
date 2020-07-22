---
<span data-ttu-id="5fd35-101">rubrik: Beskrivning av avancerade Matrix-begrepp: Lär dig mer om eigenvectors, Eigenvalues och matriser, de grundläggande verktyg som används för att beskriva och simulera Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="5fd35-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="5fd35-102">författare: QuantumWriter-UID: Microsoft. Quantum. Concepts. Matrix-Advanced MS. author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: artikeln No-Loc:</span><span class="sxs-lookup"><span data-stu-id="5fd35-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="5fd35-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-103">"$$"</span></span>
- <span data-ttu-id="5fd35-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-104">"$$"</span></span>
- <span data-ttu-id="5fd35-105">"$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-105">"$"</span></span>
- <span data-ttu-id="5fd35-106">"$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-106">"$"</span></span>
- <span data-ttu-id="5fd35-107">"$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-107">"$"</span></span>
- <span data-ttu-id="5fd35-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-108">"$$"</span></span>
- <span data-ttu-id="5fd35-109">"$$$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-109">"$$$"</span></span>
- <span data-ttu-id="5fd35-110">"$$$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-110">"$$$"</span></span>
- <span data-ttu-id="5fd35-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="5fd35-111">"$$$"</span></span>
- <span data-ttu-id="5fd35-112">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="5fd35-112">"\cdots"</span></span>
- <span data-ttu-id="5fd35-113">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="5fd35-113">"bmatrix"</span></span>
- <span data-ttu-id="5fd35-114">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="5fd35-114">"\ddots"</span></span>
- <span data-ttu-id="5fd35-115">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="5fd35-115">"\equiv"</span></span>
- <span data-ttu-id="5fd35-116">"\sum"</span><span class="sxs-lookup"><span data-stu-id="5fd35-116">"\sum"</span></span>
- <span data-ttu-id="5fd35-117">"\begin"</span><span class="sxs-lookup"><span data-stu-id="5fd35-117">"\begin"</span></span>
- <span data-ttu-id="5fd35-118">"\end"</span><span class="sxs-lookup"><span data-stu-id="5fd35-118">"\end"</span></span>
- <span data-ttu-id="5fd35-119">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="5fd35-119">"\sqrt"</span></span>
- <span data-ttu-id="5fd35-120">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="5fd35-120">"\otimes"</span></span>
- <span data-ttu-id="5fd35-121">"{"</span><span class="sxs-lookup"><span data-stu-id="5fd35-121">"{"</span></span>
- <span data-ttu-id="5fd35-122">"}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-122">"}"</span></span>
- <span data-ttu-id="5fd35-123">"\text"</span><span class="sxs-lookup"><span data-stu-id="5fd35-123">"\text"</span></span>
- <span data-ttu-id="5fd35-124">"\phi"</span><span class="sxs-lookup"><span data-stu-id="5fd35-124">"\phi"</span></span>
- <span data-ttu-id="5fd35-125">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="5fd35-125">"\kappa"</span></span>
- <span data-ttu-id="5fd35-126">"\psi"</span><span class="sxs-lookup"><span data-stu-id="5fd35-126">"\psi"</span></span>
- <span data-ttu-id="5fd35-127">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="5fd35-127">"\alpha"</span></span>
- <span data-ttu-id="5fd35-128">"\beta"</span><span class="sxs-lookup"><span data-stu-id="5fd35-128">"\beta"</span></span>
- <span data-ttu-id="5fd35-129">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="5fd35-129">"\gamma"</span></span>
- <span data-ttu-id="5fd35-130">"\delta"</span><span class="sxs-lookup"><span data-stu-id="5fd35-130">"\delta"</span></span>
- <span data-ttu-id="5fd35-131">"\omega"</span><span class="sxs-lookup"><span data-stu-id="5fd35-131">"\omega"</span></span>
- <span data-ttu-id="5fd35-132">"\bra"</span><span class="sxs-lookup"><span data-stu-id="5fd35-132">"\bra"</span></span>
- <span data-ttu-id="5fd35-133">"\ket"</span><span class="sxs-lookup"><span data-stu-id="5fd35-133">"\ket"</span></span>
- <span data-ttu-id="5fd35-134">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="5fd35-134">"\boldone"</span></span>
- <span data-ttu-id="5fd35-135">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="5fd35-135">"\\\\"</span></span>
- <span data-ttu-id="5fd35-136">"\\"</span><span class="sxs-lookup"><span data-stu-id="5fd35-136">"\\"</span></span>
- <span data-ttu-id="5fd35-137">"="</span><span class="sxs-lookup"><span data-stu-id="5fd35-137">"="</span></span>
- <span data-ttu-id="5fd35-138">"\frac"</span><span class="sxs-lookup"><span data-stu-id="5fd35-138">"\frac"</span></span>
- <span data-ttu-id="5fd35-139">"\text"</span><span class="sxs-lookup"><span data-stu-id="5fd35-139">"\text"</span></span>
- <span data-ttu-id="5fd35-140">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="5fd35-140">"\mapsto"</span></span>
- <span data-ttu-id="5fd35-141">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="5fd35-141">"\dagger"</span></span>
- <span data-ttu-id="5fd35-142">"\to"</span><span class="sxs-lookup"><span data-stu-id="5fd35-142">"\to"</span></span>
- <span data-ttu-id="5fd35-143">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-143">"\begin{cases}"</span></span>
- <span data-ttu-id="5fd35-144">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-144">"\end{cases}"</span></span>
- <span data-ttu-id="5fd35-145">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="5fd35-145">"\operatorname"</span></span>
- <span data-ttu-id="5fd35-146">"\braket"</span><span class="sxs-lookup"><span data-stu-id="5fd35-146">"\braket"</span></span>
- <span data-ttu-id="5fd35-147">"\id"</span><span class="sxs-lookup"><span data-stu-id="5fd35-147">"\id"</span></span>
- <span data-ttu-id="5fd35-148">"\expect"</span><span class="sxs-lookup"><span data-stu-id="5fd35-148">"\expect"</span></span>
- <span data-ttu-id="5fd35-149">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="5fd35-149">"\defeq"</span></span>
- <span data-ttu-id="5fd35-150">"\variance"</span><span class="sxs-lookup"><span data-stu-id="5fd35-150">"\variance"</span></span>
- <span data-ttu-id="5fd35-151">"\dd"</span><span class="sxs-lookup"><span data-stu-id="5fd35-151">"\dd"</span></span>
- <span data-ttu-id="5fd35-152">"&"</span><span class="sxs-lookup"><span data-stu-id="5fd35-152">"&"</span></span>
- <span data-ttu-id="5fd35-153">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-153">"\begin{align}"</span></span>
- <span data-ttu-id="5fd35-154">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-154">"\end{align}"</span></span>
- <span data-ttu-id="5fd35-155">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="5fd35-155">"\Lambda"</span></span>
- <span data-ttu-id="5fd35-156">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="5fd35-156">"\lambda"</span></span>
- <span data-ttu-id="5fd35-157">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="5fd35-157">"\Omega"</span></span>
- <span data-ttu-id="5fd35-158">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="5fd35-158">"\mathrm"</span></span>
- <span data-ttu-id="5fd35-159">"\left"</span><span class="sxs-lookup"><span data-stu-id="5fd35-159">"\left"</span></span>
- <span data-ttu-id="5fd35-160">"\right"</span><span class="sxs-lookup"><span data-stu-id="5fd35-160">"\right"</span></span>
- <span data-ttu-id="5fd35-161">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="5fd35-161">"\qquad"</span></span>
- <span data-ttu-id="5fd35-162">"\times"</span><span class="sxs-lookup"><span data-stu-id="5fd35-162">"\times"</span></span>
- <span data-ttu-id="5fd35-163">"\big"</span><span class="sxs-lookup"><span data-stu-id="5fd35-163">"\big"</span></span>
- <span data-ttu-id="5fd35-164">"\langle"</span><span class="sxs-lookup"><span data-stu-id="5fd35-164">"\langle"</span></span>
- <span data-ttu-id="5fd35-165">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="5fd35-165">"\rangle"</span></span>
- <span data-ttu-id="5fd35-166">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="5fd35-166">"\bigg"</span></span>
- <span data-ttu-id="5fd35-167">"\Big"</span><span class="sxs-lookup"><span data-stu-id="5fd35-167">"\Big"</span></span>
- <span data-ttu-id="5fd35-168">"|"</span><span class="sxs-lookup"><span data-stu-id="5fd35-168">"|"</span></span>
- <span data-ttu-id="5fd35-169">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="5fd35-169">"\mathbb"</span></span>
- <span data-ttu-id="5fd35-170">"\vec"</span><span class="sxs-lookup"><span data-stu-id="5fd35-170">"\vec"</span></span>
- <span data-ttu-id="5fd35-171">"\in"</span><span class="sxs-lookup"><span data-stu-id="5fd35-171">"\in"</span></span>
- <span data-ttu-id="5fd35-172">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="5fd35-172">"\texttt"</span></span>
- <span data-ttu-id="5fd35-173">"\ne"</span><span class="sxs-lookup"><span data-stu-id="5fd35-173">"\ne"</span></span>
- <span data-ttu-id="5fd35-174">"<"</span><span class="sxs-lookup"><span data-stu-id="5fd35-174">"<"</span></span>
- <span data-ttu-id="5fd35-175">">"</span><span class="sxs-lookup"><span data-stu-id="5fd35-175">">"</span></span>
- <span data-ttu-id="5fd35-176">"\leq"</span><span class="sxs-lookup"><span data-stu-id="5fd35-176">"\leq"</span></span>
- <span data-ttu-id="5fd35-177">"\geq"</span><span class="sxs-lookup"><span data-stu-id="5fd35-177">"\geq"</span></span>
- <span data-ttu-id="5fd35-178">"~~"</span><span class="sxs-lookup"><span data-stu-id="5fd35-178">"~~"</span></span>
- <span data-ttu-id="5fd35-179">"~"</span><span class="sxs-lookup"><span data-stu-id="5fd35-179">"~"</span></span>
- <span data-ttu-id="5fd35-180">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-180">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="5fd35-181">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="5fd35-181">"\end{bmatrix}"</span></span>
- <span data-ttu-id="5fd35-182">"\_"</span><span class="sxs-lookup"><span data-stu-id="5fd35-182">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="5fd35-183">Avancerade mat ris koncept</span><span class="sxs-lookup"><span data-stu-id="5fd35-183">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="5fd35-184">Vi utökar nu vår modifiering av matriser till [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) och [*exponentieller*](https://en.wikipedia.org/wiki/Matrix_exponential) som utgör en grundläggande uppsättning verktyg som vi behöver för att beskriva och implementera Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="5fd35-184">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="5fd35-185">Eigenvalues och Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="5fd35-185">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="5fd35-186">Låt $ M $ vara en fyrkantig matris och $ v $ vara en Vector som inte är en vektor som inte är noll (dvs. Vector med alla poster som är lika med $ 0 $ ).</span><span class="sxs-lookup"><span data-stu-id="5fd35-186">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="5fd35-187">Vi säger att $ v $ är en [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) av $ M $ om $ MV = ka $ för lite nummer $ c $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-187">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="5fd35-188">Vi antar att $ c $ är den [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) som motsvarar eigenvector $ v $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-188">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="5fd35-189">I allmänhet kan en matris $ M $ transformera en vektor till någon annan Vector, men en eigenvector är speciell eftersom den lämnas oförändrad, förutom om den multipliceras med ett tal.</span><span class="sxs-lookup"><span data-stu-id="5fd35-189">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="5fd35-190">Observera att om $ v $ är en eigenvector med eigenvalue $ c $ , $ är det $ också av en eigenvector (för alla som inte $ är noll a $ ) med samma eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="5fd35-190">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="5fd35-191">För Identity-matrisen är till exempel $ $ en eigenvector med eigenvalue 1 för varje Vector $ v $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-191">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="5fd35-192">Ett annat exempel är om du vill ha en [*Diagonal matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ som bara innehåller poster som inte är noll i diagonalen:</span><span class="sxs-lookup"><span data-stu-id="5fd35-192">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="5fd35-193">d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="5fd35-193">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="5fd35-194">Vektorerna</span><span class="sxs-lookup"><span data-stu-id="5fd35-194">The vectors</span></span>

$$<span data-ttu-id="5fd35-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} och \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="5fd35-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="5fd35-196">är eigenvectors i den här matrisen med Eigenvalues $ D_1 $ , $ D_2 $ $ $ respektive D_3.</span><span class="sxs-lookup"><span data-stu-id="5fd35-196">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="5fd35-197">Om $ D_1 $ , $ D_2 $ och $ D_3 $ är distinkta tal, är dessa vektorer (och deras multiplar) de enda eigenvectors i matrisen $ d $ . I allmänhet är det enkelt att läsa av Eigenvalues och eigenvectors för en diagonal matris.</span><span class="sxs-lookup"><span data-stu-id="5fd35-197">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="5fd35-198">Eigenvalues är alla siffror som visas i diagonalen och deras respektive eigenvectors är enhets vektorerna med en post lika med $ 1 $ och de återstående posterna motsvarar $ 0 $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-198">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="5fd35-199">Observera i exemplet ovan att eigenvectors i $ D $ utgör grunden för tredimensionella $ $ vektorer.</span><span class="sxs-lookup"><span data-stu-id="5fd35-199">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="5fd35-200">En basis är en uppsättning vektorer så att alla vektorer kan skrivas som en linjär kombination av dem.</span><span class="sxs-lookup"><span data-stu-id="5fd35-200">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="5fd35-201">Mer explicit, $ v_1 $ , $ v_2 $ och $ v_3 $ form a grund om en Vector $ v $ kan skrivas som $ v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ för vissa siffror $ A_1 $ , $ a_2 $ och $ a_3 $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-201">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="5fd35-202">Kom ihåg att en Hermitian-matris (även kallat eget) är en komplex fyrkantig mat ris som motsvarar dess egna komplexa konjugat, medan en enhetlig matris är en komplex fyrkantig mat ris vars invertering är lika med dess intilliggande eller komplexa konjugat.</span><span class="sxs-lookup"><span data-stu-id="5fd35-202">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="5fd35-203">För Hermitian-och enhetliga matriser, som i huvudsak är de enda matriser som påträffas i Quantum Computing, finns det ett allmänt resultat som kallas för [*Spectral-satsen*](https://en.wikipedia.org/wiki/Spectral_theorem), vilket förutsätter följande: för alla Hermitian eller en enhetlig matris $ M $ finns det en enhetlig $ U $ , till exempel $ m = u ^ \dagger D U $ för en diagonal matris $ D $ . Dessutom är de diagonala posterna i $ D $ Eigenvalues i $ M $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-203">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="5fd35-204">Vi vet redan hur man beräknar Eigenvalues och eigenvectors för en diagonal matris $ D $ . Med den här satsen vet vi att om $ v $ är en eigenvector av $ D $ med eigenvalue $ c $ , d.v.s. $ DV = ka $ , $ kommer U ^ \dagger v $ att vara en eigenvector av $ M $ med eigenvalue $ c $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-204">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="5fd35-205">Detta beror på att</span><span class="sxs-lookup"><span data-stu-id="5fd35-205">This is because</span></span>

$$<span data-ttu-id="5fd35-206">M (U ^ \dagger v) = u ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = U ^ \dagger d v = c u ^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="5fd35-206">M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="5fd35-207">Mat ris exponenter</span><span class="sxs-lookup"><span data-stu-id="5fd35-207">Matrix Exponentials</span></span>
<span data-ttu-id="5fd35-208">En [*mat ris exponent*](https://en.wikipedia.org/wiki/Matrix_exponential) kan också definieras i exakt analog till exponentiell funktionen.</span><span class="sxs-lookup"><span data-stu-id="5fd35-208">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="5fd35-209">Mat ris exponenten för en matris $ a $ kan uttryckas som</span><span class="sxs-lookup"><span data-stu-id="5fd35-209">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="5fd35-210">e ^ A = \boldone + a + a \frac { ^ 2 } { 2! } + \frac { En ^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="5fd35-210">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="5fd35-211">Detta är viktigt eftersom en Quantum mekanisk tids utveckling beskrivs av en enhetlig matris i formatet $ e ^ { IB } $ för Hermitian Matrix $ B $ .  Av den anledningen är framställningen av matriser en grundläggande del av Quantum data behandling och som t. ex. Q # innehåller inbyggda rutiner för att beskriva dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5fd35-211">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="5fd35-212">Det finns många sätt att beräkna en matris på en klassisk dator, och i stort sett en så stor uppskattning som en exponent är fraught med Peril.</span><span class="sxs-lookup"><span data-stu-id="5fd35-212">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="5fd35-213">Se [*Cleve moler och Charles Van-lånet. "Nineteen misstänkta-sätt att beräkna exponenten för en matris." SIAM granska 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) för mer information om de utmaningar som uppstår.</span><span class="sxs-lookup"><span data-stu-id="5fd35-213">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="5fd35-214">Det enklaste sättet att förstå hur du beräknar exponenten för en matris är genom Eigenvalues och eigenvectors i matrisen.</span><span class="sxs-lookup"><span data-stu-id="5fd35-214">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="5fd35-215">Mer specifikt säger Spectral-satsen ovan om att $ $ det finns en enhetlig matris $ U $ och en diagonal matris $ D $ , till exempel en $ = u ^ \dagger D u $ för varje Hermitian eller en enhetlig matris.  På grund av egenskaperna för unitarity har vi $ en ^ 2 = u ^ \dagger d ^ 2 u $ och på samma sätt för alla Power $ p $ $ A ^ p = u ^ \dagger d ^ p u $ .  Om vi ersätter detta i Operator definitionen för operatorn exponentiell, får vi:</span><span class="sxs-lookup"><span data-stu-id="5fd35-215">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="5fd35-216">e ^ a = U ^ \dagger \left ( \boldone + d + \frac { D ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 0 & \cdots & \\\\ & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="5fd35-216">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="5fd35-217">Om du till andra ord omvandlar till eigenbasis i matris A, motsvarar det att du beräknar $ $ matrisen exponentiellt för att beräkna den vanliga exponenten för Eigenvalues i matrisen.</span><span class="sxs-lookup"><span data-stu-id="5fd35-217">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="5fd35-218">Så många åtgärder som används i Quantum Computing är det här syftet med att omvandla till eigenbasis i en matris för att förenkla utförandet av operatören exponentiellt visas ofta och är grunden bakom många Quantum-algoritmer som Trotter – Suzuki Quantum simulerings metoder som beskrivs senare i den här hand boken.</span><span class="sxs-lookup"><span data-stu-id="5fd35-218">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="5fd35-219">En annan användbar egenskap är om $ B $ är både enhetligt och Hermitian, t. ex. $ b = b ^ { -1 } = B ^ \dagger $ och $ b ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="5fd35-219">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="5fd35-220">Genom att tillämpa den här regeln på ovanstående expansion av matrisen exponent och genom att gruppera $ \boldone $ och $ B $ -termerna tillsammans, kan det se att för alla verkliga värden $ x $ identiteten</span><span class="sxs-lookup"><span data-stu-id="5fd35-220">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

$$<span data-ttu-id="5fd35-221">e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="5fd35-221">e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="5fd35-222">innehålla.</span><span class="sxs-lookup"><span data-stu-id="5fd35-222">holds.</span></span> <span data-ttu-id="5fd35-223">Det här sticket är särskilt användbart eftersom det kan vara orsaken till att måtten för åtgärder i matrisen har, även om dimensionen för $ b $ är exponentiellt stor, för det särskilda fallet när $ B $ är både enhetligt och Hermitian.</span><span class="sxs-lookup"><span data-stu-id="5fd35-223">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
