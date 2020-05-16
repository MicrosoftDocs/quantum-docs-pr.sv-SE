---
title: Kvantkretsar
description: Lär dig att visuellt representera enkla och komplexa Quantum-åtgärder med Quantum-krets diagram.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f14d67db76dabda34bf881ccbfae0bfd1784ff
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426612"
---
# <a name="quantum-circuits"></a><span data-ttu-id="52aa0-103">Quantum-kretsar</span><span class="sxs-lookup"><span data-stu-id="52aa0-103">Quantum Circuits</span></span>
<span data-ttu-id="52aa0-104">Överväg att ta en stund till den enhetliga omvandlingen $ \text{CNOT} _ {01} (H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="52aa0-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="52aa0-105">Den här grind serien är av grundläggande betydelse för Quantum Computing eftersom den skapar ett maximally Entangled-qubit tillstånd:</span><span class="sxs-lookup"><span data-stu-id="52aa0-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="52aa0-106">$ $ \mathrm{CNOT}_ {01} (H\otimes 1) \ket {00} = \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="52aa0-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="52aa0-107">Åtgärder med den här eller större komplexiteten är allmänt förekommande i Quantum-algoritmer och Quantum Error-korrigering, så det bör vara en bra avläsnings metod för att det ska finnas en enkel metod för visualiseringen som kallas ett *Quantum-krets diagram*.</span><span class="sxs-lookup"><span data-stu-id="52aa0-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="52aa0-108">Krets diagrammet för att förbereda denna maximally Entangled-Quantum-tillstånd är:</span><span class="sxs-lookup"><span data-stu-id="52aa0-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-109">![Krets diagram för ett maximally-Entangled med två qubit-tillstånd](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="52aa0-110">Diagram konventioner för Quantum-kretsar</span><span class="sxs-lookup"><span data-stu-id="52aa0-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="52aa0-111">Det här visuella språket för Quantum Operations kan vara mer enkelt digestible än att skriva ned motsvarande matris när du förstår konventionerna för att uttrycka en Quantum-krets.</span><span class="sxs-lookup"><span data-stu-id="52aa0-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="52aa0-112">Vi går igenom dessa konventioner nedan.</span><span class="sxs-lookup"><span data-stu-id="52aa0-112">We review these conventions below.</span></span>

<span data-ttu-id="52aa0-113">I ett krets diagram illustrerar varje heldragen linje en qubit eller oftare i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="52aa0-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="52aa0-114">Per konvention är den översta raden qubit-registrerad $0 $ och resten märks sekventiellt.</span><span class="sxs-lookup"><span data-stu-id="52aa0-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="52aa0-115">Exempel kretsen ovan illustreras på två qubits (eller motsvarande två register som består av en qubit).</span><span class="sxs-lookup"><span data-stu-id="52aa0-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="52aa0-116">Portar som agerar på en eller flera qubit-register betecknas som en box.</span><span class="sxs-lookup"><span data-stu-id="52aa0-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="52aa0-117">Till exempel symbolen</span><span class="sxs-lookup"><span data-stu-id="52aa0-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-118">![Symbol för en Hadamard-åtgärd som agerar på ett enda qubit-register](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="52aa0-119">är en [Hadamard](xref:microsoft.quantum.intrinsic.h) -åtgärd som agerar på ett enda qubit-register.</span><span class="sxs-lookup"><span data-stu-id="52aa0-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="52aa0-120">Quantum Gates sorteras i kronologisk ordning med den översta porten som den grind som först appliceras på qubits.</span><span class="sxs-lookup"><span data-stu-id="52aa0-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="52aa0-121">Om du till exempel har en bild av kablarna som behålls i Quantum-läget, tar kablarna med Quantum-tillstånd genom varje port i diagrammet från vänster till höger.</span><span class="sxs-lookup"><span data-stu-id="52aa0-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="52aa0-122">Det vill säga</span><span class="sxs-lookup"><span data-stu-id="52aa0-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-123">![Diagram över Quantum-grindar som används från vänster till höger](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="52aa0-124">är den enhetliga matrisen $CBA $.</span><span class="sxs-lookup"><span data-stu-id="52aa0-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="52aa0-125">Matrisen multiplikation följer den motsatta konventionen: den högra matrisen används först.</span><span class="sxs-lookup"><span data-stu-id="52aa0-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="52aa0-126">I Quantum-krets diagram används dock den översta porten först.</span><span class="sxs-lookup"><span data-stu-id="52aa0-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="52aa0-127">Den här skillnaden kan ibland leda till förvirring, så det är viktigt att notera denna betydande skillnad mellan de linjära Algebraic-och Quantum-krets diagrammen.</span><span class="sxs-lookup"><span data-stu-id="52aa0-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="52aa0-128">Indata och utdata från Quantum-kretsar</span><span class="sxs-lookup"><span data-stu-id="52aa0-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="52aa0-129">Alla tidigare exempel har haft exakt samma antal tråds (qubits) inmatade i en Quantum-grind som antalet ledningar från Quantum-grinden.</span><span class="sxs-lookup"><span data-stu-id="52aa0-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="52aa0-130">Det kan först förefalla rimligt att Quantum-kretsar kan ha mer eller färre utdata än vad som är allmänt.</span><span class="sxs-lookup"><span data-stu-id="52aa0-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="52aa0-131">Detta är omöjligt, eftersom alla Quantum-åtgärder, spara mått, är enhetliga och därmed kan ångras.</span><span class="sxs-lookup"><span data-stu-id="52aa0-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="52aa0-132">Om de inte har samma antal utdata som indata kan de inte vara reversibela och därför inte vara enhetliga, vilket är en motstridighet.</span><span class="sxs-lookup"><span data-stu-id="52aa0-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="52aa0-133">En ruta som ritas i ett krets diagram måste därför ha exakt samma antal kablar som du anger när den avslutas.</span><span class="sxs-lookup"><span data-stu-id="52aa0-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="52aa0-134">Multi-qubit krets diagram följer liknande konventioner för en qubit.</span><span class="sxs-lookup"><span data-stu-id="52aa0-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="52aa0-135">Som ett exempel på ett klargörande exempel kan vi definiera en qubit-åtgärd $B $ till $ (H S\otimes X) $ och uttrycka kretsen på samma sätt som</span><span class="sxs-lookup"><span data-stu-id="52aa0-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-136">![Krets diagram över en qubit, enhetlig åtgärd](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="52aa0-137">Vi kan också Visa $B $ som har en åtgärd på ett enda qubit-register snarare än 2 1-qubit-registreringar beroende på i vilken kontext kretsen används.</span><span class="sxs-lookup"><span data-stu-id="52aa0-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="52aa0-138">Den mest användbara egenskapen för sådana abstrakta krets diagram är att de gör att komplicerade Quantum-algoritmer kan beskrivas på en hög nivå utan att behöva kompilera dem till fundamentala grindar.</span><span class="sxs-lookup"><span data-stu-id="52aa0-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="52aa0-139">Det innebär att du kan få en intuition om data flödet för en stor Quantum-algoritm utan att behöva förstå all information om hur var och en av under rutinerna i algoritmen fungerar.</span><span class="sxs-lookup"><span data-stu-id="52aa0-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="52aa0-140">Kontrollerade grindar</span><span class="sxs-lookup"><span data-stu-id="52aa0-140">Controlled gates</span></span>
<span data-ttu-id="52aa0-141">Den andra konstruktion som är inbyggd i qubit-diagram med flera är kontroll.</span><span class="sxs-lookup"><span data-stu-id="52aa0-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="52aa0-142">Åtgärden för en Quantum., som är betecknad $ \Lambda (G) $, där ett enskilt qubit värde styr programmet för $G $, kan förstås genom att titta i följande exempel på en produkt tillstånds ingång $ \Lambda (G) (\alpha \ket {0} + \beta \ket {1} ) \ket{\psi} = \alpha \ket {0} \ket{\psi} + \beta \ket {1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="52aa0-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="52aa0-143">Det vill säga att den kontrollerade porten gäller $G $ till registret som innehåller $ \psi $ om och bara om kontrollen qubit tar värdet $1 $.</span><span class="sxs-lookup"><span data-stu-id="52aa0-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="52aa0-144">I allmänhet beskriver vi sådana kontrollerade åtgärder i krets diagram som</span><span class="sxs-lookup"><span data-stu-id="52aa0-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-145">![Krets diagram över en enkel kontrollerad grind](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="52aa0-146">Här visas den svarta cirkeln som anger den Quantum-bit där porten styrs och en lodrät kabel anger den färg som tillämpas när kontrollen qubit tar värdet $1 $.</span><span class="sxs-lookup"><span data-stu-id="52aa0-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="52aa0-147">För de specialfall där $G = X $ och $G = Z $, introducerar vi följande notation för att beskriva den kontrollerade versionen av grindarna (Observera att den kontrollerade X-porten är [$CNOT $ grind](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="52aa0-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-148">![Krets diagram för särskilda fall av kontrollerade grindar](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="52aa0-149">Q # innehåller metoder för att automatiskt generera en kontrollerad version av en åtgärd, vilket sparar programmerare från att behöva gå vidare till dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="52aa0-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="52aa0-150">Ett exempel på detta visas nedan:</span><span class="sxs-lookup"><span data-stu-id="52aa0-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="52aa0-151">Mått operator</span><span class="sxs-lookup"><span data-stu-id="52aa0-151">Measurement operator</span></span>
<span data-ttu-id="52aa0-152">Den återstående åtgärden att visualisera i krets diagram är mått.</span><span class="sxs-lookup"><span data-stu-id="52aa0-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="52aa0-153">Mätningen tar ett qubit register, mäter det och matar ut resultatet som klassisk information.</span><span class="sxs-lookup"><span data-stu-id="52aa0-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="52aa0-154">En mätnings åtgärd anges av en mätar symbol och fungerar alltid som indata för ett qubit-register (betecknas med en heldragen linje) och utvärderar klassisk information (betecknas med en dubbel linje).</span><span class="sxs-lookup"><span data-stu-id="52aa0-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="52aa0-155">Mer specifikt ser en sådan under krets ut så här:</span><span class="sxs-lookup"><span data-stu-id="52aa0-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-156">![Symbol som representerar en mått åtgärd](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="52aa0-157">Q # implementerar en [mått operator](xref:microsoft.quantum.intrinsic.measure) för det här ändamålet.</span><span class="sxs-lookup"><span data-stu-id="52aa0-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="52aa0-158">Mer information finns i [avsnittet om mått](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="52aa0-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="52aa0-159">På samma sätt är under kretsen</span><span class="sxs-lookup"><span data-stu-id="52aa0-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="52aa0-160">![Krets diagram som representerar en kontrollerad åtgärd](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="52aa0-161">ger en klassisk kontrollerad grind där $G $ tillämpas på den klassiska kontroll biten som värde $1 $.</span><span class="sxs-lookup"><span data-stu-id="52aa0-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="52aa0-162">Diagram över Teleportion krets</span><span class="sxs-lookup"><span data-stu-id="52aa0-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="52aa0-163">Quantum Teleportion är kanske den bästa Quantum-algoritmen för att illustrera dessa komponenter.</span><span class="sxs-lookup"><span data-stu-id="52aa0-163">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="52aa0-164">Du kan lära dig praktisk med motsvarande [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum-teleportning i den här metoden för att flytta data i en Quantum-dator (eller till och med mellan avlägsen quantum datorer i ett Quantum-nätverk) genom att använda entanglement och mätning.</span><span class="sxs-lookup"><span data-stu-id="52aa0-164">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="52aa0-165">Det kan vara intressant att flytta ett Quantum-tillstånd, säga värdet i en specifik qubit, från en qubit till en annan, utan att ens veta vad qubit värde är!</span><span class="sxs-lookup"><span data-stu-id="52aa0-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="52aa0-166">Detta är nödvändigt för att protokollet ska fungera enligt lagstiftningen i Quantum Mechanics.</span><span class="sxs-lookup"><span data-stu-id="52aa0-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="52aa0-167">Den andra kretsen för Quantum Teleportion anges nedan. Vi tillhandahåller också en kommenterad version av kretsen för att illustrera hur du kan läsa Quantum-kretsen.</span><span class="sxs-lookup"><span data-stu-id="52aa0-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="52aa0-168">![Krets för Quantum Teleportion](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="52aa0-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
