---
title: Inbyggda funktioner och funktioner i QDK
description: Lär dig mer om de inbyggda funktionerna och funktionerna i QDK, inklusive funktioner för klassisk verksamhet, rotation och mätning.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 19674620475e68b41c855023807a5fd1f7945ec9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275665"
---
# <a name="the-prelude"></a><span data-ttu-id="4a7d3-103">Inledning</span><span class="sxs-lookup"><span data-stu-id="4a7d3-103">The Prelude</span></span> #

<span data-ttu-id="4a7d3-104">Q #-kompilatorn och mål datorerna som ingår i Quantum Development Kit innehåller en uppsättning inbyggda funktioner och åtgärder som kan användas när du skriver Quantum-program i Q #.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="4a7d3-105">Inbyggda funktioner och funktioner</span><span class="sxs-lookup"><span data-stu-id="4a7d3-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="4a7d3-106">De inbyggda åtgärder som definieras i standard biblioteket är i stort sett en av flera kategorier:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="4a7d3-107">Grundläggande klassiska funktioner som samlas in i <xref:microsoft.quantum.core> namn området.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="4a7d3-108">Åtgärder som representerar unitaries som består av [Clifford och $T $ Gates](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="4a7d3-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="4a7d3-109">Åtgärder som representerar rotationer om olika operatorer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="4a7d3-110">Åtgärder som implementerar mätningar.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-110">Operations implementing measurements.</span></span>

<span data-ttu-id="4a7d3-111">Eftersom port uppsättningen Clifford + $T $ är [universell](xref:microsoft.quantum.concepts.multiple-qubits) för Quantum Computing, räcker dessa åtgärder för att implementera alla Quantum-algoritmer inom försumbart litet fel.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="4a7d3-112">Genom att tillhandahålla rotationer kan du också använda Q # för att programmerare ska fungera inom ett enda qubit-port bibliotek med CNOT.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="4a7d3-113">Det här biblioteket är mycket enklare att tänka på eftersom programmeraren inte behöver uttrycka Clifford + $T $-dekompositionen och eftersom det finns mycket effektiva metoder för att kompilera enskilda qubit-unitaries i Clifford och $T $ Gates (mer information finns [här](xref:microsoft.quantum.more-information) ).</span><span class="sxs-lookup"><span data-stu-id="4a7d3-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="4a7d3-114">Där det är möjligt kan de åtgärder som definierats i inledning som agerar på qubits tillåta att använda `Controlled` varianten, så att mål datorn utför lämplig dekomposition.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="4a7d3-115">Många av funktionerna och åtgärderna som definierats i den här delen av inledning finns i @"microsoft.quantum.intrinsic" namn området, så att de flesta Q # källfiler har ett `open Microsoft.Quantum.Intrinsic;` direktiv direkt efter den inledande namn rymds deklarationen.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="4a7d3-116"><xref:microsoft.quantum.core>Namn området öppnas automatiskt, så att funktioner som <xref:microsoft.quantum.core.length> kan användas utan någon `open` instruktion alls.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="4a7d3-117">Vanliga åtgärder med en enda qubit</span><span class="sxs-lookup"><span data-stu-id="4a7d3-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="4a7d3-118">Inledning definierar också många vanliga [qubit-åtgärder](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="4a7d3-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="4a7d3-119">Alla dessa åtgärder tillåter både- `Controlled` och `Adjoint` functors.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="4a7d3-120">Pauli-operatörer</span><span class="sxs-lookup"><span data-stu-id="4a7d3-120">Pauli Operators</span></span> ####

<span data-ttu-id="4a7d3-121"><xref:microsoft.quantum.intrinsic.x>Åtgärden implementerar Pauli $X $-operatorn.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="4a7d3-122">Detta kallas ibland även för `NOT` porten.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="4a7d3-123">Den har signatur `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-124">Det motsvarar en qubit:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4a7d3-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: för närvarande används quadwhack hackare.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4a7d3-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4a7d3-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4a7d3-127"><xref:microsoft.quantum.intrinsic.y>Åtgärden implementerar Pauli $Y $-operatorn.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="4a7d3-128">Den har signatur `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-129">Det motsvarar en qubit:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4a7d3-130">\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % fixme: för närvarande används quadwhack Hack.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4a7d3-131">Jag & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4a7d3-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4a7d3-132"><xref:microsoft.quantum.intrinsic.z>Åtgärden implementerar Pauli $Z $-operatorn.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="4a7d3-133">Den har signatur `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-134">Det motsvarar en qubit:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4a7d3-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: för närvarande används quadwhack hackare.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4a7d3-136">0 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4a7d3-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4a7d3-137">Nedan visas dessa omvandlingar som är kopplade till [Bloch-sfären](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (rotations axeln i varje fall är markerad som röd):</span><span class="sxs-lookup"><span data-stu-id="4a7d3-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Pauli-åtgärder som har mappats till Bloch-sfären](~/media/prelude_pauliBloch.png)

<span data-ttu-id="4a7d3-139">Det är viktigt att Observera att att tillämpa samma Pauli-grind två gånger på samma qubit avbryter åtgärden (eftersom du nu har utfört en fullständig rotation av 2π (360 °) över ytan till Bloch-sfären, och därmed kommer tillbaka vid start punkten).</span><span class="sxs-lookup"><span data-stu-id="4a7d3-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="4a7d3-140">Detta ger oss följande identitet:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-140">This brings us to the following identity:</span></span>

<span data-ttu-id="4a7d3-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="4a7d3-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="4a7d3-142">Detta kan vara visualised på Bloch-sfären:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="4a7d3-144">Annan qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="4a7d3-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="4a7d3-145"><xref:microsoft.quantum.intrinsic.h>Åtgärden implementerar Hadamard-porten.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="4a7d3-146">Detta förändrar Pauli-$X $ och $Z $-axlarna i mål qubit, till exempel $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ och $H \ket{+} = \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="4a7d3-147">Den innehåller en signatur `(Qubit => Unit is Adj + Ctl)` och motsvarar den enda-qubit-enhetliga:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4a7d3-148">\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: för närvarande används quadwhack hacka.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4a7d3-149">1 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4a7d3-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="4a7d3-150">Hadamard-porten är särskilt viktig eftersom den kan användas för att skapa en superposition för $ \ket {0} $ och $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="4a7d3-151">I sfär representationen Bloch är det enklast att tänka på detta som en rotation av $ \ket{\psi} $ runt x-axeln med $ \pi $ radianer ($ 180 ^ \circ $) följt av en rotation på y-axeln med $ \ Pi/2 $ radianer ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="4a7d3-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Hadamard-åtgärd mappad till Bloch-sfären](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="4a7d3-153"><xref:microsoft.quantum.intrinsic.s>Åtgärden implementerar fas porten $S $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="4a7d3-154">Detta är matrisen för matrisen Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="4a7d3-155">Det vill säga $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="4a7d3-156">Den innehåller en signatur `(Qubit => Unit is Adj + Ctl)` och motsvarar den enda-qubit-enhetliga:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="4a7d3-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: för närvarande används quadwhack hackare.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="4a7d3-158">0 & i \end{bmatrix}-\end{Equation}</span><span class="sxs-lookup"><span data-stu-id="4a7d3-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="4a7d3-159">Rotation</span><span class="sxs-lookup"><span data-stu-id="4a7d3-159">Rotations</span></span> ####

<span data-ttu-id="4a7d3-160">Utöver Pauli-och Clifford-åtgärderna ovan tillhandahåller Q # inledning en mängd olika sätt att uttrycka rotationer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="4a7d3-161">Som beskrivs i [en qubit-åtgärd](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)är möjligheten att rotera kritiskt för Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="4a7d3-162">Vi börjar med att komma ihåg att vi kan uttrycka en enskild qubit-åtgärd med hjälp av $H $ och $T $-grindarna, där $H $ är Hadamard-åtgärden och där \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: det här använder för närvarande Whack hackare.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="4a7d3-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} detta är kvadratroten av <xref:microsoft.quantum.intrinsic.s> åtgärden, till exempel $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="4a7d3-164">$T $-porten implementeras av <xref:microsoft.quantum.intrinsic.t> åtgärden och har en signatur som `(Qubit => Unit is Adj + Ctl)` anger att det är en enhetlig åtgärd på en enskild-qubit.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="4a7d3-165">Även om detta är i princip tillräckligt för att beskriva en godtycklig enskild qubit-åtgärd kan olika mål datorer ha mer effektiva representationer för rotationer om Pauli-operatörer, till exempel att inledning innehåller en mängd olika sätt att convienently Express sådana rotationer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="4a7d3-166">De flesta av dessa är <xref:microsoft.quantum.intrinsic.r> åtgärden, som implementerar en rotation runt en angiven Pauli-axel, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} där $ \sigma $ är en Pauli-operatör, $ \phi $ är en vinkel och där $ \exp $ representerar matrisen exponent.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="4a7d3-167">Den innehåller en signatur `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` där de första två delarna i indatamängden representerar de klassiska argumenten $ \sigma $ och $ \phi $ som krävs för att ange den enhetliga operatorn $R (\sigma, \phi) $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="4a7d3-168">Vi kan delvis använda $ \sigma $ och $ \phi $ för att få en åtgärd vars typ är en enda-qubit-enhetlig.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="4a7d3-169">Har till exempel `R(PauliZ, PI() / 4, _)` typen `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="4a7d3-170"><xref:microsoft.quantum.intrinsic.r>Åtgärden delar upp ingångs vinkeln med 2 och multiplicerar den med-1.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="4a7d3-171">För $Z $-rotationer innebär detta att $ \ket {0} $ eigenstate roteras av $-\phi/$2 och att $ \ket {1} $ eigenstate roteras med $ \phi/$2, så att $ \ket {1} $ eigenstate roteras med $ \phi $ i förhållande till $ \ket {0} $ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="4a7d3-172">Detta innebär särskilt att `T` och `R(PauliZ, PI() / 8, _)` bara skiljer sig från en irrelevant [Global fas](xref:microsoft.quantum.glossary#global-phase).</span><span class="sxs-lookup"><span data-stu-id="4a7d3-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="4a7d3-173">Av den anledningen kallas $T $ $ \frac{\pi} {8} $-grind.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="4a7d3-174">Observera också att när du roterar runt `PauliI` bara tillämpas en global fas av $ \phi/$2.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="4a7d3-175">Även om dessa faser är irrelevanta, så som vi anförde i [de konceptuella dokumenten](xref:microsoft.quantum.concepts.qubit), är de relevanta för kontrollerade `PauliI` rotationer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="4a7d3-176">I Quantum-algoritmer är det ofta användbart att uttrycka rotationer som dyadic bråktal, till exempel $ \phi = \pi k/2 ^ n $ för vissa $k \in \mathbb{Z} $ och $n \in \mathbb{N} $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="4a7d3-177"><xref:microsoft.quantum.intrinsic.rfrac>Åtgärden implementerar en rotation runt en angiven Pauli axel med denna konvention.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="4a7d3-178">Det skiljer sig från <xref:microsoft.quantum.intrinsic.r> i att rotations vinkeln har angetts som två indata av typen `Int` , tolkas som en dyadic fraktion.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="4a7d3-179">Därför `RFrac` har signatur `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-180">Den implementerar en qubit-\exp (i \pi k \sigma/2 ^ n) $, där $ \sigma $ är den Pauli matris som motsvarar det första argumentet, $k $ är det andra argumentet och $n $ är det tredje argumentet.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="4a7d3-181">`RFrac(_,k,n,_)`är detsamma som `R(_,-πk/2^n,_)` . Observera att vinkeln är *negativ* för bråket.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="4a7d3-182"><xref:microsoft.quantum.intrinsic.rx>Åtgärden implementerar en rotation runt Pauli-$X $-axeln.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="4a7d3-183">Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-184">`Rx(_, _)`är samma som `R(PauliX, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="4a7d3-185"><xref:microsoft.quantum.intrinsic.ry>Åtgärden implementerar en rotation runt Pauli-$Y $-axeln.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="4a7d3-186">Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-187">`Ry(_, _)`är samma som `R(PauliY,_ , _)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="4a7d3-188"><xref:microsoft.quantum.intrinsic.rz>Åtgärden implementerar en rotation runt Pauli-$Z $-axeln.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="4a7d3-189">Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-190">`Rz(_, _)`är samma som `R(PauliZ, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="4a7d3-191"><xref:microsoft.quantum.intrinsic.r1>Åtgärden implementerar en rotation med den mängd som finns runt $ \ket {1} $, $-$1-eigenstate för $Z $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="4a7d3-192">Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-193">`R1(phi,_)`är detsamma som `R(PauliZ,phi,_)` följt av `R(PauliI,-phi,_)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="4a7d3-194"><xref:microsoft.quantum.intrinsic.r1frac>Åtgärden implementerar en fraktions rotation med den mängd som finns runt Z = 1-eigenstate.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="4a7d3-195">Den har signatur `((Int,Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-196">`R1Frac(k,n,_)`är detsamma som `RFrac(PauliZ,-k.n+1,_)` följt av `RFrac(PauliI,k,n+1,_)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="4a7d3-197">Ett exempel på en rotations åtgärd (runt Pauli $Z $-axeln, i den här instansen) som är mappad till Bloch-sfären visas nedan:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Rotations åtgärd som är mappad till Bloch-sfären](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="4a7d3-199">Multi-qubit-åtgärder</span><span class="sxs-lookup"><span data-stu-id="4a7d3-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="4a7d3-200">Förutom de enskilda qubit-åtgärderna ovan definierar inledning också flera åtgärder för flera qubit.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="4a7d3-201">Först <xref:microsoft.quantum.intrinsic.cnot> utför åtgärden en kontrollerad- `NOT` grind, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="4a7d3-202">\end{Equation} den har signatur `((Qubit, Qubit) => Unit is Adj + Ctl)` , som representerar $ \operatorname{CNOT} $ agerar unitarily på två enskilda qubits.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="4a7d3-203">`CNOT(q1, q2)`är samma som `(Controlled X)([q1], q2)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="4a7d3-204">Eftersom `Controlled` Functor gör det möjligt att kontrol lera ett register använder vi mat ris strängen `[q1]` för att indikera att vi bara vill ha den enda kontrollen.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="4a7d3-205"><xref:microsoft.quantum.intrinsic.ccnot>Åtgärden utför dubblerad-styrd icke-grind, ibland även kallat Toffoli-porten.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="4a7d3-206">Den har signatur `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-207">`CCNOT(q1, q2, q3)`är samma som `(Controlled X)([q1, q2], q3)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="4a7d3-208"><xref:microsoft.quantum.intrinsic.swap>Åtgärden byter ut Quantum-tillstånden för två qubits.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="4a7d3-209">Det innebär att den implementerar den enhetliga matrisen \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="4a7d3-210">\end{Equation} den har signatur `((Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4a7d3-211">`SWAP(q1,q2)`motsvarar `CNOT(q1, q2)` följt av `CNOT(q2, q1)` och sedan `CNOT(q1, q2)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="4a7d3-212">VÄXLINGs porten är *inte* samma sak som att ordna om elementen i en variabel med typ `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="4a7d3-213">`SWAP(q1, q2)`Att tillämpa gör en ändring i status för den qubits som refereras till av `q1` och `q2` , men `let swappedRegister = [q2, q1];` påverkar bara hur vi refererar till dessa qubits.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="4a7d3-214">Dessutom `(Controlled SWAP)([q0], (q1, q2))` gör det möjligt `SWAP` att villkorligt godkännas för en tredje qubit, som vi inte kan representera genom att arrangera om element.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="4a7d3-215">Den övervakade VÄXLINGs porten, som även kallas Fredkin-grind, är tillräckligt kraftfull för att inkludera all klassisk beräkning.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="4a7d3-216">Slutligen tillhandahåller inledning två åtgärder för att representera exponenter för multi-qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="4a7d3-217"><xref:microsoft.quantum.intrinsic.exp>Åtgärden utför en rotation baserat på en behållen produkt i Pauli-matriser. som representeras av multi-qubit-\Begin{Equation} \operatorname{exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} där $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ är en följd av en vinkel.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="4a7d3-218">`Exp`Rotationen representerar $ \vec{\sigma} $ som en matris med `Pauli` element, till exempel signaturen `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="4a7d3-219"><xref:microsoft.quantum.intrinsic.expfrac>Åtgärden utför samma rotation med dyadic bråk notationen som beskrivs ovan.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="4a7d3-220">Den har signatur `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="4a7d3-221">Pauli-operatörernas exponenter är inte samma som för bevarans produkter av Pauli-operatörernas exponenter.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="4a7d3-222">Det vill säga $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="4a7d3-223">Mått</span><span class="sxs-lookup"><span data-stu-id="4a7d3-223">Measurements</span></span> ###

<span data-ttu-id="4a7d3-224">Vid mätningen motsvarar + 1-eigenvalue för den operator som mäts till ett `Zero` resultat och eigenvalue-1-till ett `One` resultat.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="4a7d3-225">Även om denna konvention kan verka ojämn, har den två mycket bra fördelar.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="4a7d3-226">För det första visas resultatet $ \ket {0} $ av `Result` värdet `Zero` , samtidigt som $ \ket {1} $ motsvarar `One` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="4a7d3-227">Sedan kan vi skriva ut att eigenvalue $ \lambda $ som motsvarar resultatet $r $ är $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="4a7d3-228">Mått åtgärder stöder varken `Adjoint` eller `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="4a7d3-229"><xref:microsoft.quantum.intrinsic.measure>Åtgärden utför en gemensam mätning av en eller flera qubits i den angivna produkten av Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="4a7d3-230">Om Pauli-matrisen och qubit-matrisen har olika längd, Miss lyckas åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="4a7d3-231">`Measure`har signatur `((Pauli[], Qubit[]) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="4a7d3-232">Observera att en gemensam mätning inte är samma som att mäta varje qubit individuellt.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="4a7d3-233">Anta till exempel tillstånd $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="4a7d3-234">Mätning $Z _0 $ och $Z _1 $ var för sig får du resultaten $r _0 = $1 och $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="4a7d3-235">Mätning $Z _0 Z_1 $, men vi får ett enda resultat $r _ {\textrm{joint}} = $0, som visar att paret $ \ket {11} $ är positivt.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="4a7d3-236">Sätt på olika sätt, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="4a7d3-237">Eftersom vi *bara* lär dig paritet från den här mätningen bevaras alla Quantum-uppgifter som representeras i superpositionen mellan 2 2-qubit-tillstånden för positiv paritet, $ \ket {00} $ och $ \ket {11} $.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="4a7d3-238">Den här egenskapen är viktig senare, eftersom vi diskuterar fel korrigering.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="4a7d3-239">För enkelhetens skull tillhandahåller inledning också två andra åtgärder för att mäta qubits.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="4a7d3-240">För det första, eftersom det är ganska vanligt att utföra qubit mätningar definierar inledning en kort skrift för det här fallet.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="4a7d3-241"><xref:microsoft.quantum.intrinsic.m>Åtgärden mäter Pauli $Z $-operatorn på en enskild qubit och har signatur `(Qubit => Result)` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="4a7d3-242">`M(q)`motsvarar `Measure([PauliZ], [q])` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="4a7d3-243"><xref:microsoft.quantum.measurement.multim>Måtten Pauli $Z $-operatören *var separat* på var och en av qubits, och returnerar *matrisen* med `Result` värden som hämtats för varje qubit.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="4a7d3-244">I vissa fall kan detta optimeras.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-244">In some cases this can be optimized.</span></span> <span data-ttu-id="4a7d3-245">Den har signatur ( `Qubit[] => Result[])` .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="4a7d3-246">`MultiM(qs)`motsvarar:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="4a7d3-247">Funktioner och åtgärder för tillägg</span><span class="sxs-lookup"><span data-stu-id="4a7d3-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="4a7d3-248">Dessutom definierar inledning en omfattande uppsättning matematiska och typ konverterings funktioner på .NET-nivån för användning inom Q # Code.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="4a7d3-249">Till exempel <xref:microsoft.quantum.math> definierar namn området användbara åtgärder som <xref:microsoft.quantum.math.sin> och <xref:microsoft.quantum.math.log> .</span><span class="sxs-lookup"><span data-stu-id="4a7d3-249">For instance, the <xref:microsoft.quantum.math> namespace defines useful operations such as <xref:microsoft.quantum.math.sin> and <xref:microsoft.quantum.math.log>.</span></span>
<span data-ttu-id="4a7d3-250">Den implementering som tillhandahålls av Quantum Development Kit använder det klassiska .NET-klass biblioteket och kan därmed omfatta en ytterligare överföring av kommunikation mellan Quantum-program och deras klassiska driv rutiner.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="4a7d3-251">Även om detta inte visar något problem för en lokal simulator kan detta vara ett prestanda problem när du använder en fjärrsimulator eller en faktisk maskin vara som mål dator.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="4a7d3-252">I detta fall kan en enskild måldator minimera den här prestanda påverkan genom att åsidosätta dessa åtgärder med versioner som är mer effektiva för det specifika systemet.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="4a7d3-253">Matematik</span><span class="sxs-lookup"><span data-stu-id="4a7d3-253">Math</span></span> ###

<span data-ttu-id="4a7d3-254"><xref:microsoft.quantum.math>Namn området innehåller många användbara funktioner i .NET Base Class-bibliotekets [ `System.Math` klass](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span><span class="sxs-lookup"><span data-stu-id="4a7d3-254">The <xref:microsoft.quantum.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="4a7d3-255">Dessa funktioner kan användas på samma sätt som andra Q #-funktioner:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="4a7d3-256">Om en statisk metod för .NET har överlagrats baserat på typen av argument är motsvarande Q #-funktion kommenterad med ett suffix som anger indatatypen:</span><span class="sxs-lookup"><span data-stu-id="4a7d3-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="4a7d3-257">Bitvisa åtgärder</span><span class="sxs-lookup"><span data-stu-id="4a7d3-257">Bitwise Operations</span></span> ###

<span data-ttu-id="4a7d3-258">Slutligen <xref:microsoft.quantum.bitwise> tillhandahåller namn området flera användbara funktioner för att manipulera heltal genom bitvisa operatorer.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-258">Finally, the <xref:microsoft.quantum.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="4a7d3-259">Returnerar till exempel <xref:microsoft.quantum.bitwise.parity> den bitvisa pariteten för ett heltal som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="4a7d3-259">For instance, <xref:microsoft.quantum.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
