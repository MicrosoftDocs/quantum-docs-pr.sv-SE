---
title: Ord lista för Quantum Computing
description: En ord lista med vanliga termer, åtgärder och objekt som används i Quantum Computing.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630095"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="0156f-103">Ord lista för Quantum Computing</span><span class="sxs-lookup"><span data-stu-id="0156f-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="0156f-104">Angränsande</span><span class="sxs-lookup"><span data-stu-id="0156f-104">Adjoint</span></span>

<span data-ttu-id="0156f-105">Den komplexa konjugats transponeren för en [åtgärd](xref:microsoft.quantum.glossary#operation).</span><span class="sxs-lookup"><span data-stu-id="0156f-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="0156f-106">För åtgärder som implementerar en [enhetlig](xref:microsoft.quantum.glossary#unitary-operator) operator är det intilliggande är inversen till åtgärden och anges av en Dagger symbol.</span><span class="sxs-lookup"><span data-stu-id="0156f-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="0156f-107">Om åtgärden till exempel `U` representerar den enhetliga operatorn $U $ , `Adjoint U` representerar $U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="0156f-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="0156f-108">Mer information finns i [angränsande](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="0156f-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="0156f-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="0156f-109">Ancilla</span></span>

<span data-ttu-id="0156f-110">En [qubit](xref:microsoft.quantum.glossary#qubit) som fungerar som temporärt minne för en Quantum-dator och allokeras och avallokeras efter behov.</span><span class="sxs-lookup"><span data-stu-id="0156f-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="0156f-111">Mer information finns i [flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="0156f-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="0156f-112">Klock status</span><span class="sxs-lookup"><span data-stu-id="0156f-112">Bell state</span></span>

<span data-ttu-id="0156f-113">Ett av fyra olika maximally [Entangled](xref:microsoft.quantum.glossary#entanglement) [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) för två qubits.</span><span class="sxs-lookup"><span data-stu-id="0156f-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="0156f-114">De fyra tillstånden definieras $ \ket { \ beta_ { } } = (\Mathbb{I } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="0156f-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="0156f-115">En klock status kallas även för ett [EPR-par](xref:microsoft.quantum.glossary#epr-pair).</span><span class="sxs-lookup"><span data-stu-id="0156f-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="0156f-116">Bloch-sfär</span><span class="sxs-lookup"><span data-stu-id="0156f-116">Bloch sphere</span></span>

<span data-ttu-id="0156f-117">En grafisk representation av ett[qubit](xref:microsoft.quantum.glossary#qubit) [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) som en punkt i ett tredimensionellt enhets klot.</span><span class="sxs-lookup"><span data-stu-id="0156f-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="0156f-118">Mer information finns i [visualisera qubits och omvandlingar med hjälp av Bloch-sfären](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="0156f-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="0156f-119">Anropningsbara</span><span class="sxs-lookup"><span data-stu-id="0156f-119">Callable</span></span>

<span data-ttu-id="0156f-120">En [funktion](xref:microsoft.quantum.glossary#operation) eller [funktion](xref:microsoft.quantum.glossary#function) på språket Q #.</span><span class="sxs-lookup"><span data-stu-id="0156f-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="0156f-121">Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="0156f-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="0156f-122">Clifford-grupp</span><span class="sxs-lookup"><span data-stu-id="0156f-122">Clifford group</span></span>

<span data-ttu-id="0156f-123">Den uppsättning åtgärder som upptar octants för Bloch- [sfären](xref:microsoft.quantum.glossary#bloch-sphere) och [Pauli-operatörernas-operatorer](xref:microsoft.quantum.glossary#pauli-operators).</span><span class="sxs-lookup"><span data-stu-id="0156f-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="0156f-124">Detta omfattar åtgärder [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z), [$H $ ](xref:microsoft.quantum.intrinsic.h) och [$S $ ](xref:microsoft.quantum.intrinsic.s).</span><span class="sxs-lookup"><span data-stu-id="0156f-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="0156f-125">Styr</span><span class="sxs-lookup"><span data-stu-id="0156f-125">Controlled</span></span>

<span data-ttu-id="0156f-126">En Quantum- [åtgärd](xref:microsoft.quantum.glossary#operation) som tar en eller flera [qubits](xref:microsoft.quantum.glossary#qubit) som aktiveringar för mål åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0156f-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="0156f-127">Mer information finns i [kontrollerade och närliggande aktiviteter](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="0156f-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="0156f-128">Dirac-notation</span><span class="sxs-lookup"><span data-stu-id="0156f-128">Dirac Notation</span></span>

<span data-ttu-id="0156f-129">Ett symboliskt kort som fören klar åter givningen av [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state), även kallat *bra-ket* notation.</span><span class="sxs-lookup"><span data-stu-id="0156f-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="0156f-130">*Bra* -delen representerar en rad vektor, till exempel $ \bra{A } = \begin{ bmatrix } a {_1 } & a {_2 } \end{ bmatrix } $ och *ket* -delen representerar en kolumn vektor, $ \ket{B } = \begin{ bmatrix } b {_1 } \\ \\ b {_2 } \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="0156f-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="0156f-131">Mer information finns i [Dirac notation](xref:microsoft.quantum.concepts.dirac).</span><span class="sxs-lookup"><span data-stu-id="0156f-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="0156f-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="0156f-132">Eigenvalue</span></span>

<span data-ttu-id="0156f-133">Den faktor enligt vilken storleken på en [eigenvector](xref:microsoft.quantum.glossary#eigenvector) för en specifik omvandling ändras av omvandlingens program.</span><span class="sxs-lookup"><span data-stu-id="0156f-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="0156f-134">Om du har fått en fyrkantig matris $M $ och en eigenvector $v $ $MV = ka $ , där $c $ är eigenvalue och kan vara ett komplext antal argument.</span><span class="sxs-lookup"><span data-stu-id="0156f-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="0156f-135">Mer information finns i [avancerade mat ris koncept](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="0156f-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="0156f-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="0156f-136">Eigenvector</span></span>

<span data-ttu-id="0156f-137">En Vector vars riktning är oförändrad av en specifik omvandling och vars storlek ändras av en faktor som motsvarar den Vectorns [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span><span class="sxs-lookup"><span data-stu-id="0156f-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="0156f-138">Om du har fått en fyrkantig matris $M $ och en eigenvalue $c $ $MV = ka $ , där $v $ är en eigenvector i matrisen och kan vara ett komplext antal argument.</span><span class="sxs-lookup"><span data-stu-id="0156f-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="0156f-139">Mer information finns i [avancerade mat ris koncept](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="0156f-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="0156f-140">Sammanflätning</span><span class="sxs-lookup"><span data-stu-id="0156f-140">Entanglement</span></span>

<span data-ttu-id="0156f-141">Quantum-partiklar, till exempel [qubits](xref:microsoft.quantum.glossary#qubit), kan vara anslutna eller *Entangled* så att de inte kan beskrivas oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="0156f-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="0156f-142">Deras mått resultat korreleras även om de avgränsas oändligt långt bort.</span><span class="sxs-lookup"><span data-stu-id="0156f-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="0156f-143">Entanglement är viktigt för [measuring](xref:microsoft.quantum.glossary#measurement) att mäta [status](xref:microsoft.quantum.glossary#quantum-state) för en qubit.</span><span class="sxs-lookup"><span data-stu-id="0156f-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="0156f-144">Mer information finns i [avancerade mat ris koncept](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="0156f-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="0156f-145">EPR-par</span><span class="sxs-lookup"><span data-stu-id="0156f-145">EPR pair</span></span>

<span data-ttu-id="0156f-146">Ett av fyra olika maximally Entangled [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) för två [qubits](xref:microsoft.quantum.glossary#qubit).</span><span class="sxs-lookup"><span data-stu-id="0156f-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="0156f-147">De fyra tillstånden definieras $ \ket { \ beta_ { } } = (\Mathbb{1 } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="0156f-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="0156f-148">Ett EPR-par kallas även för [klock status](xref:microsoft.quantum.glossary#bell-state)</span><span class="sxs-lookup"><span data-stu-id="0156f-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="0156f-149">Utveckling</span><span class="sxs-lookup"><span data-stu-id="0156f-149">Evolution</span></span>

<span data-ttu-id="0156f-150">Hur ett [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) ändras med tiden.</span><span class="sxs-lookup"><span data-stu-id="0156f-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="0156f-151">Mer information finns i [matriss exponentieller](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span><span class="sxs-lookup"><span data-stu-id="0156f-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="0156f-152">Funktion</span><span class="sxs-lookup"><span data-stu-id="0156f-152">Function</span></span>
<span data-ttu-id="0156f-153">En typ av subrutin på det Q #-språk som är helt Klassiskt (icke-Quantum).</span><span class="sxs-lookup"><span data-stu-id="0156f-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="0156f-154">Medan Functions används i Quantum-algoritmer, kan de inte agera på [qubits](xref:microsoft.quantum.glossary#qubit) -eller anrops [åtgärder](xref:microsoft.quantum.glossary#operation).</span><span class="sxs-lookup"><span data-stu-id="0156f-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="0156f-155">Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="0156f-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="0156f-156">Gate</span><span class="sxs-lookup"><span data-stu-id="0156f-156">Gate</span></span>

<span data-ttu-id="0156f-157">En äldre term för en Quantum- [åtgärd](xref:microsoft.quantum.glossary#operation)baserat på begreppet klassiska Logic-grindar.</span><span class="sxs-lookup"><span data-stu-id="0156f-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="0156f-158">En [Quantum-krets](xref:microsoft.quantum.glossary#quantum-circuit-diagram) är ett nätverk av portar (eller åtgärder), baserat på liknande koncept av klassiska Logic-kretsar.</span><span class="sxs-lookup"><span data-stu-id="0156f-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="0156f-159">Global fas</span><span class="sxs-lookup"><span data-stu-id="0156f-159">Global phase</span></span>

<span data-ttu-id="0156f-160">När två [tillstånd](xref:microsoft.quantum.glossary#quantum-state) är identiska med en multipel av ett komplext tal $e ^ {i \phi } $, är de på samma sätt som en global fas.</span><span class="sxs-lookup"><span data-stu-id="0156f-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="0156f-161">Till skillnad från lokala faser går det inte att observera globala faser genom något [mätbart mätbart](xref:microsoft.quantum.glossary#measurement)behov.</span><span class="sxs-lookup"><span data-stu-id="0156f-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="0156f-162">Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="0156f-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="0156f-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="0156f-163">Hadamard</span></span>

<span data-ttu-id="0156f-164">Hadamard-åtgärden (kallas även Hadamard-grind eller transformering) fungerar på en enda [qubit](xref:microsoft.quantum.glossary#qubit) och placerar den i ett jämnt [överplacerat](xref:microsoft.quantum.glossary#superposition) $ \ket{0 } $ eller $ \ket{1 } $ om qubit är inlednings vis i $ \ket{0 } $ State.</span><span class="sxs-lookup"><span data-stu-id="0156f-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="0156f-165">I Q # tillämpas den här åtgärden av den fördefinierade [`H`](xref:microsoft.quantum.intrinsic.h) åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0156f-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="0156f-166">Inte kan ändras</span><span class="sxs-lookup"><span data-stu-id="0156f-166">Immutable</span></span>

<span data-ttu-id="0156f-167">En variabel vars värde inte kan ändras.</span><span class="sxs-lookup"><span data-stu-id="0156f-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="0156f-168">En oföränderlig variabel i Q # skapas med hjälp av `let` nyckelordet.</span><span class="sxs-lookup"><span data-stu-id="0156f-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="0156f-169">Om du vill deklarera variabler som *kan* ändras använder du nyckelordet [föränderligt](xref:microsoft.quantum.glossary#immutable) för att deklarera och `set` nyckelordet för att ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="0156f-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="0156f-170">Mått</span><span class="sxs-lookup"><span data-stu-id="0156f-170">Measurement</span></span>

<span data-ttu-id="0156f-171">En manipulering av en [qubit](xref:microsoft.quantum.glossary#qubit) (eller en uppsättning qubits) som ger resultatet av en observation, och som hämtar en klassisk bit.</span><span class="sxs-lookup"><span data-stu-id="0156f-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="0156f-172">Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span><span class="sxs-lookup"><span data-stu-id="0156f-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="0156f-173">Föränderlig</span><span class="sxs-lookup"><span data-stu-id="0156f-173">Mutable</span></span>

<span data-ttu-id="0156f-174">En variabel vars värde kan ändras efter att det har skapats.</span><span class="sxs-lookup"><span data-stu-id="0156f-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="0156f-175">En föränderligt-variabel i Q # deklareras med hjälp av `mutable` nyckelordet och modifieras med hjälp av `set` nyckelordet.</span><span class="sxs-lookup"><span data-stu-id="0156f-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="0156f-176">Variabler som skapas med `let` nyckelordet är [oföränderliga](xref:microsoft.quantum.glossary#immutable) och deras värde kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="0156f-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="0156f-177">Namnområde</span><span class="sxs-lookup"><span data-stu-id="0156f-177">Namespace</span></span>

<span data-ttu-id="0156f-178">En etikett för en samling relaterade namn (t. ex. [åtgärder](xref:microsoft.quantum.glossary#operation), [funktioner](xref:microsoft.quantum.glossary#function)och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type)).</span><span class="sxs-lookup"><span data-stu-id="0156f-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="0156f-179">Till exempel märks namn området [Microsoft. Quantum. Preparation](xref:microsoft.quantum.preparation) med alla symboler som definierats i standard biblioteket som hjälper till att förbereda de ursprungliga tillstånden.</span><span class="sxs-lookup"><span data-stu-id="0156f-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="0156f-180">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="0156f-180">Operation</span></span>

<span data-ttu-id="0156f-181">Den grundläggande enheten för Quantum-körning i Q #.</span><span class="sxs-lookup"><span data-stu-id="0156f-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="0156f-182">Det är ungefär detsamma som en funktion i C, C++ eller python, eller en statisk metod i C# eller Java.</span><span class="sxs-lookup"><span data-stu-id="0156f-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="0156f-183">Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="0156f-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="0156f-184">Operatörs program</span><span class="sxs-lookup"><span data-stu-id="0156f-184">Operator application</span></span>

<span data-ttu-id="0156f-185">Utföra en Quantum-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0156f-185">Performing a quantum operation.</span></span> <span data-ttu-id="0156f-186">Detta använder vanligt vis en enhetlig matris till den aktuella Quantum-delläges vektorn.</span><span class="sxs-lookup"><span data-stu-id="0156f-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="0156f-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="0156f-187">Oracle</span></span>

<span data-ttu-id="0156f-188">En subrutin som tillhandahåller data beroende information till en Quantum-algoritm vid körning.</span><span class="sxs-lookup"><span data-stu-id="0156f-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="0156f-189">Målet är vanligt vis att ge en [superposition](xref:microsoft.quantum.glossary#superposition) av utdata som motsvarar indata som är i position.</span><span class="sxs-lookup"><span data-stu-id="0156f-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="0156f-190">Mer information finns i [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span><span class="sxs-lookup"><span data-stu-id="0156f-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="0156f-191">Partiellt program</span><span class="sxs-lookup"><span data-stu-id="0156f-191">Partial application</span></span>

<span data-ttu-id="0156f-192">Anropa en [funktion](xref:microsoft.quantum.glossary#function) eller [åtgärd](xref:microsoft.quantum.glossary#operation) utan alla nödvändiga indata.</span><span class="sxs-lookup"><span data-stu-id="0156f-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="0156f-193">Detta returnerar en ny [uppringning](xref:microsoft.quantum.glossary#callable) som bara behöver de parametrar som saknas (vilket indikeras av ett under streck) som ska levereras under ett framtida program.</span><span class="sxs-lookup"><span data-stu-id="0156f-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="0156f-194">Till exempel `MyFunc(x : int, y : int) : int {return x + y;}` kan du använda funktionen för att delvis tillämpa den på en ny funktion `let NewFunc = MyFunc(_, 3)` .</span><span class="sxs-lookup"><span data-stu-id="0156f-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="0156f-195">Du kan sedan anropa den nya funktionen vid ett senare tillfälle med den saknade parametern `NewFunc(2)` som returnerar värdet *5*.</span><span class="sxs-lookup"><span data-stu-id="0156f-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="0156f-196">Mer information finns i [partiellt program](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span><span class="sxs-lookup"><span data-stu-id="0156f-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="0156f-197">Pauli-operatörer</span><span class="sxs-lookup"><span data-stu-id="0156f-197">Pauli operators</span></span>

<span data-ttu-id="0156f-198">En uppsättning med tre 2 x 2-matriser som kallas `X` , `Y` och Quantum- `Z` åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0156f-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="0156f-199">Identitets mat ris $I $ , ingår ofta även i uppsättningen.</span><span class="sxs-lookup"><span data-stu-id="0156f-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="0156f-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="0156f-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="0156f-201">Mer information finns i [åtgärder med en qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="0156f-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="0156f-202">Diagram över Quantum-krets</span><span class="sxs-lookup"><span data-stu-id="0156f-202">Quantum circuit diagram</span></span>

<span data-ttu-id="0156f-203">En metod för att grafiskt representera en sekvens med [åtgärder](xref:microsoft.quantum.glossary#operation) (eller [portar](xref:microsoft.quantum.glossary#gate)) för enkla Quantum-program, till exempel</span><span class="sxs-lookup"><span data-stu-id="0156f-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![Diagram över exempel krets](~/media/qpe.png)<span data-ttu-id="0156f-205">.</span><span class="sxs-lookup"><span data-stu-id="0156f-205">.</span></span> 

<span data-ttu-id="0156f-206">Mer information finns i [Quantum-kretsar](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="0156f-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="0156f-207">Quantum-bibliotek</span><span class="sxs-lookup"><span data-stu-id="0156f-207">Quantum libraries</span></span>

<span data-ttu-id="0156f-208">Samlingar med [åtgärder](xref:microsoft.quantum.glossary#operation), [funktioner](xref:microsoft.quantum.glossary#function) och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type) för att skapa Q #-program.</span><span class="sxs-lookup"><span data-stu-id="0156f-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="0156f-209">[Standard biblioteket](xref:microsoft.quantum.libraries.standard.intro) installeras som standard.</span><span class="sxs-lookup"><span data-stu-id="0156f-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="0156f-210">Andra tillgängliga bibliotek är [kemi-biblioteket](xref:microsoft.quantum.chemistry.concepts.intro), det [numeriska biblioteket](xref:microsoft.quantum.numerics.intro) och [Machine Learning-biblioteket](xref:microsoft.quantum.machine-learning.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="0156f-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="0156f-211">Quantum-tillstånd</span><span class="sxs-lookup"><span data-stu-id="0156f-211">Quantum state</span></span>

<span data-ttu-id="0156f-212">Det exakta läget för ett isolerat Quantum-system, från vilket [mått](xref:microsoft.quantum.glossary#measurement) sannolikheter kan extraheras.</span><span class="sxs-lookup"><span data-stu-id="0156f-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="0156f-213">I Quantum Computing använder Quantum Simulator den här informationen för att simulera hur qubits reagerar på åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0156f-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="0156f-214">Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="0156f-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="0156f-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="0156f-215">Qubit</span></span>

<span data-ttu-id="0156f-216">En grundläggande enhet med Quantum-information som motsvarar en *bit* i klassisk data behandling.</span><span class="sxs-lookup"><span data-stu-id="0156f-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="0156f-217">Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="0156f-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="0156f-218">Upprepa-tills-lyckades</span><span class="sxs-lookup"><span data-stu-id="0156f-218">Repeat-until-success</span></span>

<span data-ttu-id="0156f-219">En Quantum-algoritm som probabilistically lyckas.</span><span class="sxs-lookup"><span data-stu-id="0156f-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="0156f-220">Vid fel försöker rutinen igen tills den lyckades (eller så har en gräns nåtts).</span><span class="sxs-lookup"><span data-stu-id="0156f-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="0156f-221">Mer information finns i [Upprepa tills lyckad (ru: er)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="0156f-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="0156f-222">Standardbibliotek</span><span class="sxs-lookup"><span data-stu-id="0156f-222">Standard libraries</span></span>

<span data-ttu-id="0156f-223">[Åtgärder](xref:microsoft.quantum.glossary#operation), [funktioner](xref:microsoft.quantum.glossary#function) och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type) som installeras tillsammans med Q #-kompilatorn under installationen.</span><span class="sxs-lookup"><span data-stu-id="0156f-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="0156f-224">Standard biblioteks implementeringen är oberoende med avseende på mål datorer.</span><span class="sxs-lookup"><span data-stu-id="0156f-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="0156f-225">Mer information finns i [standard bibliotek](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="0156f-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="0156f-226">Superposition</span><span class="sxs-lookup"><span data-stu-id="0156f-226">Superposition</span></span>

<span data-ttu-id="0156f-227">Konceptet i Quantum Computing som en [qubit](xref:microsoft.quantum.glossary#qubit) är en linjär kombination av två tillstånd, $ \ket{0 } $ och $ \ket{1 } $, tills den [mäts](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="0156f-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="0156f-228">Mer information finns i [förstå Quantum Computing](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="0156f-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="0156f-229">Måldator</span><span class="sxs-lookup"><span data-stu-id="0156f-229">Target machine</span></span>

<span data-ttu-id="0156f-230">Ett Compilation Target som sänker ett abstrakt Quantum-program mot maskin vara eller simulering.</span><span class="sxs-lookup"><span data-stu-id="0156f-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="0156f-231">Detta omfattar vanligt vis åter skrivningar för många olika sätt, inklusive porttyp, kodning för fel korrigering, geometrisk layout och andra.</span><span class="sxs-lookup"><span data-stu-id="0156f-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="0156f-232">Mer information finns i [Quantum Simulators och värd program](xref:microsoft.quantum.machines).</span><span class="sxs-lookup"><span data-stu-id="0156f-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="0156f-233">Teleportering</span><span class="sxs-lookup"><span data-stu-id="0156f-233">Teleportation</span></span>

<span data-ttu-id="0156f-234">En metod för att återskapa data eller Quantum- [tillstånd](xref:microsoft.quantum.glossary#quantum-state)för en [qubit](xref:microsoft.quantum.glossary#qubit) från en plats till en annan utan att fysiskt flytta qubit, med hjälp av [entanglement](xref:microsoft.quantum.glossary#entanglement) och [mätning](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="0156f-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="0156f-235">Mer information finns i [Quantum-kretsar](xref:microsoft.quantum.concepts.circuits) och respektive Kata vid [Quantum Katas](xref:microsoft.quantum.overview.katas).</span><span class="sxs-lookup"><span data-stu-id="0156f-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="0156f-236">Tupel</span><span class="sxs-lookup"><span data-stu-id="0156f-236">Tuple</span></span>

<span data-ttu-id="0156f-237">En samling kommaavgränsade värden som fungerar som ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="0156f-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="0156f-238">*Typen* av en tupel definieras av de typer av värden som den innehåller.</span><span class="sxs-lookup"><span data-stu-id="0156f-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="0156f-239">I Q # är tupler [oföränderliga](xref:microsoft.quantum.glossary#immutable) och kan kapslas, innehålla matriser eller användas i en matris.</span><span class="sxs-lookup"><span data-stu-id="0156f-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="0156f-240">Mer information finns i [tuple-typer](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="0156f-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="0156f-241">Enhetlig operatör</span><span class="sxs-lookup"><span data-stu-id="0156f-241">Unitary operator</span></span>

<span data-ttu-id="0156f-242">En operator vars motsatta värde är lika med den [angränsande](xref:microsoft.quantum.glossary#adjoint), d.v.s. $uu ^ {\dagger } = \id $ .</span><span class="sxs-lookup"><span data-stu-id="0156f-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="0156f-243">Användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="0156f-243">User-defined type</span></span>

<span data-ttu-id="0156f-244">En samling inbyggda eller tidigare definierade typer som kan kallas en enda enhet.</span><span class="sxs-lookup"><span data-stu-id="0156f-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="0156f-245">Mer information finns i [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="0156f-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>