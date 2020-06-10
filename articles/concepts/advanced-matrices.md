---
title: Avancerade matrisbegrepp
description: Lär dig mer om eigenvectors, Eigenvalues och Matrix-exponenter, de grundläggande verktyg som används för att beskriva och simulera Quantum-algoritmer.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630156"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="32ba3-103">Avancerade mat ris koncept</span><span class="sxs-lookup"><span data-stu-id="32ba3-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="32ba3-104">Vi utökar nu vår modifiering av matriser till [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) och [*exponentieller*](https://en.wikipedia.org/wiki/Matrix_exponential) som utgör en grundläggande uppsättning verktyg som vi behöver för att beskriva och implementera Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="32ba3-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="32ba3-105">Eigenvalues och Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="32ba3-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="32ba3-106">Låt $M $ vara en kvadratisk matris och $v $ vara en Vector som inte är en vektor som inte är noll (dvs. Vector med alla poster som är lika med $0 $ ).</span><span class="sxs-lookup"><span data-stu-id="32ba3-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="32ba3-107">Vi antar $ att $v är en [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) av $M $ om $MV = ka $ för en viss siffra $c $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="32ba3-108">Vi antar att $c $ är den [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) som motsvarar eigenvector $v $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="32ba3-109">I allmänhet kan en matris $M $ omvandla en vektor till någon annan Vector, men en eigenvector är speciell eftersom den lämnas oförändrad, förutom om den multipliceras med ett tal.</span><span class="sxs-lookup"><span data-stu-id="32ba3-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="32ba3-110">Observera att om $v $ är en eigenvector med eigenvalue $c $ , är $av $ också en eigenvector (för alla $a som inte $ är noll) med samma eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="32ba3-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="32ba3-111">Till exempel, för identitets mat ris, är varje Vector $v $ en eigenvector med eigenvalue $1 $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="32ba3-112">Ett annat exempel är om du vill ha en [*Diagonal matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ som bara innehåller poster som inte är noll i diagonalen:</span><span class="sxs-lookup"><span data-stu-id="32ba3-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="32ba3-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="32ba3-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="32ba3-114">d_1 & 0 & 0 \\ \\ 0 & D_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="32ba3-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="32ba3-115">Vektorerna</span><span class="sxs-lookup"><span data-stu-id="32ba3-115">The vectors</span></span>

<span data-ttu-id="32ba3-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } och \begin{ bmatrix } 0 0 \\ \\ \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="32ba3-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="32ba3-117">är eigenvectors i matrisen med Eigenvalues $d _1 $ , $d _2 $ och $d _3 $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="32ba3-118">Om $d _1 $ , $d _2 $ och $d _3 $ är distinkta tal, är dessa vektorer (och deras multiplar) de enda eigenvectors för mat ris $D $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="32ba3-119">I allmänhet är det enkelt att läsa av Eigenvalues och eigenvectors för en diagonal matris.</span><span class="sxs-lookup"><span data-stu-id="32ba3-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="32ba3-120">Eigenvalues är alla siffror som visas i diagonalen och deras respektive eigenvectors är enhets vektorerna med en post som motsvarar $1 $ och de återstående posterna som motsvarar $0 $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="32ba3-121">Observera i exemplet ovan att $D eigenvectors $ utgör grunden för $3 $ -dimensionella vektorer.</span><span class="sxs-lookup"><span data-stu-id="32ba3-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="32ba3-122">En basis är en uppsättning vektorer så att alla vektorer kan skrivas som en linjär kombination av dem.</span><span class="sxs-lookup"><span data-stu-id="32ba3-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="32ba3-123">Mer explicit, $v _1 $ , $v _2 $ och $v _3 $ form a-basis om någon Vector $v $ kan skrivas som $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ för vissa siffror $a _1 $ , $a _2 $ och $a _3 $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="32ba3-124">Kom ihåg att en Hermitian-matris (även kallat eget) är en komplex fyrkantig mat ris som motsvarar dess egna komplexa konjugat, medan en enhetlig matris är en komplex fyrkantig mat ris vars invertering är lika med dess komplexa konjugat.</span><span class="sxs-lookup"><span data-stu-id="32ba3-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="32ba3-125">För Hermitian-och enhetliga matriser, som i huvudsak är de enda matriser som påträffas i Quantum Computing, finns det ett allmänt resultat som kallas för [*Spectral-satsen*](https://en.wikipedia.org/wiki/Spectral_theorem), vilket förutsätter följande: för alla Hermitian eller enhetliga matriser $M finns $ det en enhetlig $U $ som $M = U ^ \dagger D U $ för viss Diagonal matris $D $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="32ba3-126">Dessutom är de diagonala posterna för $D $ Eigenvalues av $M $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="32ba3-127">Vi vet redan hur man beräknar Eigenvalues och eigenvectors för en diagonal matris $D $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="32ba3-128">Med den här satsen vet vi att om $v $ är en eigenvector av $D $ med eigenvalue $c $ , d.v.s. $DV = ka $ , kommer $U ^ \dagger v $ att vara en eigenvector av $M $ med eigenvalue $c $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="32ba3-129">Detta beror på att</span><span class="sxs-lookup"><span data-stu-id="32ba3-129">This is because</span></span>

<span data-ttu-id="32ba3-130">$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="32ba3-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="32ba3-131">Mat ris exponenter</span><span class="sxs-lookup"><span data-stu-id="32ba3-131">Matrix Exponentials</span></span>
<span data-ttu-id="32ba3-132">En [*mat ris exponent*](https://en.wikipedia.org/wiki/Matrix_exponential) kan också definieras i exakt analog till exponentiell funktionen.</span><span class="sxs-lookup"><span data-stu-id="32ba3-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="32ba3-133">Matrisens exponentiella $A $ kan uttryckas som</span><span class="sxs-lookup"><span data-stu-id="32ba3-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="32ba3-134">$ $ e ^ A = \boldone + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="32ba3-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="32ba3-135">Detta är viktigt eftersom den resulterande mekaniska tids utvecklingen beskrivs av en enhetlig matris i formuläret $e ^ {iB } $ för Hermitian matrix $B $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="32ba3-136">Av den anledningen är framställningen av matriser en grundläggande del av Quantum data behandling och som t. ex. Q # innehåller inbyggda rutiner för att beskriva dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="32ba3-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="32ba3-137">Det finns många sätt att beräkna en matris på en klassisk dator, och i stort sett en så stor uppskattning som en exponent är fraught med Peril.</span><span class="sxs-lookup"><span data-stu-id="32ba3-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="32ba3-138">Se [*Cleve moler och Charles Van-lånet. "Nineteen misstänkta-sätt att beräkna exponenten för en matris." SIAM granska 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) för mer information om de utmaningar som uppstår.</span><span class="sxs-lookup"><span data-stu-id="32ba3-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="32ba3-139">Det enklaste sättet att förstå hur du beräknar exponenten för en matris är genom Eigenvalues och eigenvectors i matrisen.</span><span class="sxs-lookup"><span data-stu-id="32ba3-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="32ba3-140">Mer specifikt säger Spectral-satsen ovan att för varje Hermitian eller en enhetlig matris $A $ det finns en enhetlig matris $U $ och en diagonal mat ris $D $ som $A = U ^ \dagger D U $ .  På grund av egenskaperna för unitarity har vi $A ^ 2 = U ^ \dagger D ^ 2 U $ och på samma sätt för alla power $p $ $A ^ p = U ^ \dagger D ^ p U $ .  Om vi ersätter detta i Operator definitionen för operatorn exponentiell, får vi:</span><span class="sxs-lookup"><span data-stu-id="32ba3-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="32ba3-141">$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="32ba3-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="32ba3-142">Om du till andra ord omvandlar till eigenbasis i matrisen $A, $ motsvarar den vanliga exponenten för Eigenvalues i matrisen.</span><span class="sxs-lookup"><span data-stu-id="32ba3-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="32ba3-143">Så många åtgärder som används i Quantum Computing är det här syftet med att omvandla till eigenbasis i en matris för att förenkla utförandet av operatören exponentiellt visas ofta och är grunden bakom många Quantum-algoritmer som Trotter – Suzuki Quantum simulerings metoder som beskrivs senare i den här hand boken.</span><span class="sxs-lookup"><span data-stu-id="32ba3-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="32ba3-144">En annan användbar egenskap är om $B $ är både enhetligt och Hermitian, d.v.s. $B = b ^ {-1 } = B ^ \dagger $ sedan $B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="32ba3-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="32ba3-145">Genom att tillämpa den här regeln på ovanstående expansion av matrisen exponent och genom att gruppera $ \boldone $ och de $B $ villkoren tillsammans, kan det se att för alla verkliga värden $x $ identiteten</span><span class="sxs-lookup"><span data-stu-id="32ba3-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="32ba3-146">$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="32ba3-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="32ba3-147">innehålla.</span><span class="sxs-lookup"><span data-stu-id="32ba3-147">holds.</span></span> <span data-ttu-id="32ba3-148">Det här sticket är särskilt användbart eftersom det kan vara orsaken till att måtten för åtgärder i matrisen har, även om dimensionen för $B $ är exponentiellt stor för det särskilda fallet när $B $ är både enhetligt och Hermitian.</span><span class="sxs-lookup"><span data-stu-id="32ba3-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
