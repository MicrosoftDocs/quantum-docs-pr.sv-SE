---
title: Vektorer och matriser i kvantberäkning
description: Lär dig grunderna för hur du arbetar med vektorer och matriser.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269549"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="71f9d-103">Vektorer och matriser</span><span class="sxs-lookup"><span data-stu-id="71f9d-103">Vectors and Matrices</span></span>

<span data-ttu-id="71f9d-104">En del bekant med vektorer och matriser är viktigt för att förstå Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="71f9d-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="71f9d-105">Vi ger en kort introduktion nedan och intresserade läsare rekommenderas att läsa en standard referens för linjära algebra, till exempel *Strang, G. (1993). Introduktion till linjär algebra (vol. 3). Wellesley, MA: Wellesley-Cambridge press* eller a online Reference, till exempel [linjär algebra](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="71f9d-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="71f9d-106">En kolumn vektor (eller bara [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ av dimension (eller storlek) $n $ är en samling $n $ komplexa tal $ (v_1, v_2, \ldots, V_n) $ ordnade som en kolumn:</span><span class="sxs-lookup"><span data-stu-id="71f9d-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="71f9d-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-108">v_1\\\\</span></span>
<span data-ttu-id="71f9d-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-109">v_2\\\\</span></span>
<span data-ttu-id="71f9d-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-110">\vdots\\\\</span></span>
<span data-ttu-id="71f9d-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="71f9d-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="71f9d-112">Normen för en Vector $v $ definieras som $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $.</span><span class="sxs-lookup"><span data-stu-id="71f9d-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="71f9d-113">En Vector anses vara av enhets norm (eller också kallas den för en [*enhets vektor*](https://en.wikipedia.org/wiki/Unit_vector)) om dess norm är $1 $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="71f9d-114">Det [*angränsande av en vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ betecknas $v ^ \dagger $ och definieras som följande rad vektor där $ \* $ anger det komplexa konjugatet.</span><span class="sxs-lookup"><span data-stu-id="71f9d-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="71f9d-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ V_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ \* & \cdots & V_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="71f9d-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="71f9d-116">Det vanligaste sättet att multiplicera två vektorer är genom den [*inre produkten*](https://en.wikipedia.org/wiki/Inner_product_space), även kallat en punkt produkt.</span><span class="sxs-lookup"><span data-stu-id="71f9d-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="71f9d-117">Den inre produkten ger projektionen av en Vector till en annan och är värdefull för att beskriva hur man uttrycker en Vector som en summa av andra enklare vektorer.</span><span class="sxs-lookup"><span data-stu-id="71f9d-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="71f9d-118">Den inre produkten mellan $u $ och $v $ , betecknad $ \left \langle u, v \right \rangle $ definieras som</span><span class="sxs-lookup"><span data-stu-id="71f9d-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="71f9d-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="71f9d-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="71f9d-120">Den här notationen tillåter också att en Vector $ -$v skrivs som $ \sqrt { \langle v, v \rangle } $.</span><span class="sxs-lookup"><span data-stu-id="71f9d-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="71f9d-121">Vi kan multiplicera en Vector med en siffra $c $ för att forma en ny Vector vars poster multipliceras med $c $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="71f9d-122">Vi kan också lägga till två vektorer $u $ och $v $ för att skapa en ny Vector vars poster är summan av posterna för $u $ och $v $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="71f9d-123">Dessa åtgärder beskrivs nedan:</span><span class="sxs-lookup"><span data-stu-id="71f9d-123">These operations are depicted below:</span></span>

<span data-ttu-id="71f9d-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-125">u_1\\\\</span></span>
<span data-ttu-id="71f9d-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-126">u_2\\\\</span></span>
<span data-ttu-id="71f9d-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-127">\vdots\\\\</span></span>
<span data-ttu-id="71f9d-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-129">v_1\\\\</span></span>
    <span data-ttu-id="71f9d-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-130">v_2\\\\</span></span>
    <span data-ttu-id="71f9d-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-131">\vdots\\\\</span></span>
    <span data-ttu-id="71f9d-132">V_n \end{ bmatrix } ~ \mathrm{then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="71f9d-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="71f9d-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-135">\vdots\\\\</span></span>
<span data-ttu-id="71f9d-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="71f9d-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="71f9d-137">En [*matris*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) med storlek $m \times n $ är en samling $mn $ komplexa tal ordnade i $m $ rader och $n $ kolumner enligt nedan:</span><span class="sxs-lookup"><span data-stu-id="71f9d-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="71f9d-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-139">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="71f9d-140">M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="71f9d-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="71f9d-141">Observera att en Vector med dimensions $n $ bara är en mat ris med storlek $n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="71f9d-142">Precis som med vektorer kan vi multiplicera en matris med en siffra $c $ för att hämta en ny matris där varje post multipliceras med $c $ , och vi kan lägga till två matriser av samma storlek för att skapa en ny matris vars poster är summan av respektive poster för de två matriserna.</span><span class="sxs-lookup"><span data-stu-id="71f9d-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="71f9d-143">Matris-och beskrivares produkter</span><span class="sxs-lookup"><span data-stu-id="71f9d-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="71f9d-144">Vi kan också multiplicera två matriser $M $ av dimensions $m \times n $ och $N $ för dimension $n \times p $ för att få en ny mat ris $P $ för dimension $m \times p $ enligt följande:</span><span class="sxs-lookup"><span data-stu-id="71f9d-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="71f9d-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="71f9d-145">\begin{align}</span></span>
<span data-ttu-id="71f9d-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-147">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="71f9d-148">M_ {M1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn}</span><span class="sxs-lookup"><span data-stu-id="71f9d-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="71f9d-149">ändamålbmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-149">\end{bmatrix}</span></span>
<span data-ttu-id="71f9d-150">kopplingbmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-150">\begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1P } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="71f9d-152">N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {NP}</span><span class="sxs-lookup"><span data-stu-id="71f9d-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="71f9d-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1P } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="71f9d-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {MP}</span><span class="sxs-lookup"><span data-stu-id="71f9d-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="71f9d-156">ändamålbmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-156">\end{bmatrix}</span></span>
<span data-ttu-id="71f9d-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="71f9d-157">\end{align}</span></span>

<span data-ttu-id="71f9d-158">om posterna för $P $ är $P _ {IK } = \ sum_j M_ {jk} N_ { } $.</span><span class="sxs-lookup"><span data-stu-id="71f9d-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="71f9d-159">Posten $P _ {11 $ är till exempel } den inre produkten av den första raden i $M $ med den första kolumnen i $N $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="71f9d-160">Observera att eftersom en Vector bara är ett specialfall av en matris, sträcker sig denna definition till multiplikation med mat ris vektorer.</span><span class="sxs-lookup"><span data-stu-id="71f9d-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="71f9d-161">Alla matriser som vi anser är antingen fyrkantiga matriser, där antalet rader och kolumner är lika med, eller vektorer, som motsvarar endast $1 $ kolumn.</span><span class="sxs-lookup"><span data-stu-id="71f9d-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="71f9d-162">En speciell hak mat ris är [*identitets mat*](https://en.wikipedia.org/wiki/Identity_matrix)ris, med namnet $ \boldone $ , som har alla dess diagonala element lika med $1 $ och återstående element som är lika med $0 $ :</span><span class="sxs-lookup"><span data-stu-id="71f9d-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="71f9d-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="71f9d-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="71f9d-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="71f9d-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="71f9d-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="71f9d-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="71f9d-168">För en fyrkantig mat ris $A $ säger vi att en matris $B $ är [*inversen*](https://en.wikipedia.org/wiki/Invertible_matrix) om $AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="71f9d-169">Inversen till en matris behöver inte finnas, men när den finns är den unik och vi betecknar den $A ^ {-1 } $.</span><span class="sxs-lookup"><span data-stu-id="71f9d-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="71f9d-170">För alla matriser $M $ är den angränsande eller konjugatingen av $M $ en mat ris $N $ som $N _ { } Ji = M_ { } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="71f9d-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="71f9d-171">Det angränsande $M $ är vanligt vis betecknad $M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="71f9d-172">Vi antar att en matris $U $ är [*enhetlig*](https://en.wikipedia.org/wiki/Unitary_matrix) om $UU ^ \dagger = U ^ \dagger U = \boldone $ eller motsvarande, $U ^ {-1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="71f9d-173">Kanske är den viktigaste egenskapen för enhetliga matriser att de behåller normen i en Vector.</span><span class="sxs-lookup"><span data-stu-id="71f9d-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="71f9d-174">Detta inträffar eftersom</span><span class="sxs-lookup"><span data-stu-id="71f9d-174">This happens because</span></span> 

<span data-ttu-id="71f9d-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, U v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="71f9d-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="71f9d-176">En mat ris $M anses $ vara [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) om $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="71f9d-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="71f9d-177">Slutligen är bevarans [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (eller Kronecker produkt) av två matriser $M $ storlek $m \times n $ och $N $ av storlek $p \times q $ är en större matris $P = M \otimes n $ av storlek $MP \times NQ $ och hämtas från $M $ och $N $ enligt följande:</span><span class="sxs-lookup"><span data-stu-id="71f9d-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="71f9d-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="71f9d-178">\begin{align}</span></span>
    <span data-ttu-id="71f9d-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-180">M_ {11 } ~ ~ \cdots ~ ~ M_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="71f9d-181">M_ {M1 } ~ ~ \cdots ~ ~ M_ {mn}</span><span class="sxs-lookup"><span data-stu-id="71f9d-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="71f9d-182">ändamålbmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-182">\end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-184">N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="71f9d-185">N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ}</span><span class="sxs-lookup"><span data-stu-id="71f9d-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="71f9d-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1N } \begin{ bmatrix } N_ {11 ~ ~ \cdots ~ ~ N_ {1Q \ddots } } \\ \\ \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="71f9d-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="71f9d-188">M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {mn } \begin{N_ {11 ~ ~ \cdots ~ ~ N_ {1Q \ddots bmatrix } } N_ { } \\ \\ \\\\ P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="71f9d-189">\end{bmatrix}.</span></span>
<span data-ttu-id="71f9d-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="71f9d-190">\end{align}</span></span>

<span data-ttu-id="71f9d-191">Detta demonstreras bättre med några exempel:</span><span class="sxs-lookup"><span data-stu-id="71f9d-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="71f9d-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-194">en \begin{ bmatrix } c \\ \\ d \\ \\ e-\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="71f9d-195">\\\\[1,5 EM] b \begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-196">ändamålbmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-196">\end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-197">= \begin{ bmatrix } a c a \\ \\ d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="71f9d-198">och</span><span class="sxs-lookup"><span data-stu-id="71f9d-198">and</span></span>

<span data-ttu-id="71f9d-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="71f9d-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="71f9d-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-204">en\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-206">t\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-208">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-210">styr\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-212">ändamålbmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-212">\end{bmatrix}</span></span>
    <span data-ttu-id="71f9d-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="71f9d-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="71f9d-214">AE \ AF \ var \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ CE \ CF \ de \ DF \\ \\ CG \ CH \ GD \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="71f9d-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="71f9d-215">En slutgiltig, användbar, utgångs konvention som omger betecknings produkter är att, för alla vektor $v $ eller matris $M $ , $v ^ {\otimes n } $ eller $M ^ {\otimes n } $ är kort hand för en $n med $ upprepade Skriv medel.</span><span class="sxs-lookup"><span data-stu-id="71f9d-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="71f9d-216">Exempel:</span><span class="sxs-lookup"><span data-stu-id="71f9d-216">For example:</span></span>

<span data-ttu-id="71f9d-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="71f9d-217">\begin{align}</span></span>
<span data-ttu-id="71f9d-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{1 0 0 bmatrix } \\ \\ \\ \\ \\ \\ \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1-1 \\ \\ -1 \\ \\ \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ & 0 \end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 \\ \\ \\\\ \end{bmatrix} &0&1&0 &0&0&0.</span><span class="sxs-lookup"><span data-stu-id="71f9d-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="71f9d-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="71f9d-219">\end{align}</span></span>
