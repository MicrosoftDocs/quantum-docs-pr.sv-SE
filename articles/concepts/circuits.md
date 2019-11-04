---
title: Quantum-kretsar | Microsoft Docs
description: Quantum-kretsar
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210626"
---
# <a name="quantum-circuits"></a><span data-ttu-id="4f986-103">Quantum-kretsar</span><span class="sxs-lookup"><span data-stu-id="4f986-103">Quantum Circuits</span></span>
<span data-ttu-id="4f986-104">Överväg att ta en stund till den enhetliga omvandlingen $ \text{CNOT} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="4f986-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="4f986-105">Den här grind serien är av grundläggande betydelse för Quantum Computing eftersom den skapar ett maximally Entangled-qubit tillstånd:</span><span class="sxs-lookup"><span data-stu-id="4f986-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="4f986-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="4f986-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="4f986-107">Åtgärder med den här eller större komplexiteten är allmänt förekommande i Quantum-algoritmer och Quantum Error-korrigering, så det bör vara en bra avläsnings metod för att det ska finnas en enkel metod för visualiseringen som kallas ett *Quantum-krets diagram*.</span><span class="sxs-lookup"><span data-stu-id="4f986-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="4f986-108">Krets diagrammet för att förbereda denna maximally Entangled-Quantum-tillstånd är:</span><span class="sxs-lookup"><span data-stu-id="4f986-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="4f986-109">Diagram konventioner för Quantum-kretsar</span><span class="sxs-lookup"><span data-stu-id="4f986-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="4f986-110">Det här visuella språket för Quantum Operations kan vara mer enkelt digestible än att skriva ned motsvarande matris när du förstår konventionerna för att uttrycka en Quantum-krets.</span><span class="sxs-lookup"><span data-stu-id="4f986-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="4f986-111">Vi går igenom dessa konventioner nedan.</span><span class="sxs-lookup"><span data-stu-id="4f986-111">We review these conventions below.</span></span>

<span data-ttu-id="4f986-112">I ett krets diagram illustrerar varje heldragen linje en qubit eller oftare i ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="4f986-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="4f986-113">Per konvention är den översta raden qubit-registrerad $0 $ och resten märks sekventiellt.</span><span class="sxs-lookup"><span data-stu-id="4f986-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="4f986-114">Exempel kretsen ovan illustreras på två qubits (eller motsvarande två register som består av en qubit).</span><span class="sxs-lookup"><span data-stu-id="4f986-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="4f986-115">Portar som agerar på en eller flera qubit-register betecknas som en box.</span><span class="sxs-lookup"><span data-stu-id="4f986-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="4f986-116">Till exempel symbolen</span><span class="sxs-lookup"><span data-stu-id="4f986-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="4f986-117">är [Hadamard](xref:microsoft.quantum.primitive.h) -porten som agerar vid en qubit-registrering.</span><span class="sxs-lookup"><span data-stu-id="4f986-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="4f986-118">Quantum Gates sorteras i kronologisk ordning med den översta porten som den grind som först appliceras på qubits.</span><span class="sxs-lookup"><span data-stu-id="4f986-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="4f986-119">Om du till exempel har en bild av kablarna som behålls i Quantum-läget, tar kablarna med Quantum-tillstånd genom varje port i diagrammet från vänster till höger.</span><span class="sxs-lookup"><span data-stu-id="4f986-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="4f986-120">Det vill säga</span><span class="sxs-lookup"><span data-stu-id="4f986-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="4f986-121">är den enhetliga matrisen $CBA $.</span><span class="sxs-lookup"><span data-stu-id="4f986-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="4f986-122">Matrisen multiplikation följer den motsatta konventionen: den högra matrisen används först.</span><span class="sxs-lookup"><span data-stu-id="4f986-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="4f986-123">I Quantum-krets diagram används dock den översta porten först.</span><span class="sxs-lookup"><span data-stu-id="4f986-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="4f986-124">Den här skillnaden kan ibland leda till förvirring, så det är viktigt att notera denna betydande skillnad mellan de linjära Algebraic-och Quantum-krets diagrammen.</span><span class="sxs-lookup"><span data-stu-id="4f986-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="4f986-125">Indata och utdata från Quantum-kretsar</span><span class="sxs-lookup"><span data-stu-id="4f986-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="4f986-126">Alla tidigare exempel har haft exakt samma antal tråds (qubits) inmatade i en Quantum-grind som antalet ledningar från Quantum-grinden.</span><span class="sxs-lookup"><span data-stu-id="4f986-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="4f986-127">Det kan först förefalla rimligt att Quantum-kretsar kan ha mer eller färre utdata än vad som är allmänt.</span><span class="sxs-lookup"><span data-stu-id="4f986-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="4f986-128">Detta är omöjligt, eftersom alla Quantum-åtgärder, spara mått, är enhetliga och därmed kan ångras.</span><span class="sxs-lookup"><span data-stu-id="4f986-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="4f986-129">Om de inte har samma antal utdata som indata kan de inte vara reversibela och därför inte vara enhetliga, vilket är en motstridighet.</span><span class="sxs-lookup"><span data-stu-id="4f986-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="4f986-130">En ruta som ritas i ett krets diagram måste därför ha exakt samma antal kablar som du anger när den avslutas.</span><span class="sxs-lookup"><span data-stu-id="4f986-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="4f986-131">Multi-qubit krets diagram följer liknande konventioner för en qubit.</span><span class="sxs-lookup"><span data-stu-id="4f986-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="4f986-132">Som ett exempel på ett klargörande exempel kan vi definiera en qubit-åtgärd $B $ till $ (H S\otimes X) $ och uttrycka kretsen på samma sätt som</span><span class="sxs-lookup"><span data-stu-id="4f986-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="4f986-133">Vi kan också Visa $B $ som har en åtgärd på ett enda qubit-register snarare än 2 1-qubit-registreringar beroende på i vilken kontext kretsen används.</span><span class="sxs-lookup"><span data-stu-id="4f986-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="4f986-134">Den mest användbara egenskapen för sådana abstrakta krets diagram är att de gör att komplicerade Quantum-algoritmer kan beskrivas på en hög nivå utan att behöva kompilera dem till fundamentala grindar.</span><span class="sxs-lookup"><span data-stu-id="4f986-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="4f986-135">Det innebär att du kan få en intuition om data flödet för en stor Quantum-algoritm utan att behöva förstå all information om hur var och en av under rutinerna i algoritmen fungerar.</span><span class="sxs-lookup"><span data-stu-id="4f986-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="4f986-136">Kontrollerade grindar</span><span class="sxs-lookup"><span data-stu-id="4f986-136">Controlled gates</span></span>
<span data-ttu-id="4f986-137">Den andra konstruktion som är inbyggd i qubit-diagram med flera är kontroll.</span><span class="sxs-lookup"><span data-stu-id="4f986-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="4f986-138">Åtgärden för en Quantum och lätt kontrollerad grind, som betecknar $ \Lambda (G) $, där ett enskilt qubit värde styr programmet för $G $, kan förstås genom att titta i följande exempel på en produkt tillstånds ingång $ \Lambda (G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="4f986-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="4f986-139">Det vill säga att den kontrollerade porten gäller $G $ till registret som innehåller $ \psi $ om och bara om kontrollen qubit tar värdet $1 $.</span><span class="sxs-lookup"><span data-stu-id="4f986-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="4f986-140">I allmänhet beskriver vi sådana kontrollerade åtgärder i krets diagram som</span><span class="sxs-lookup"><span data-stu-id="4f986-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="4f986-141">Här visas den svarta cirkeln som anger den Quantum-bit där porten styrs och en lodrät kabel anger den färg som tillämpas när kontrollen qubit tar värdet $1 $.</span><span class="sxs-lookup"><span data-stu-id="4f986-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="4f986-142">För de specialfall där $G = X $ och $G = Z $, introducerar vi följande notation för att beskriva den kontrollerade versionen av grindarna (Observera att den kontrollerade X-porten är [$CNOT $ grind](xref:microsoft.quantum.primitive.cnot)):</span><span class="sxs-lookup"><span data-stu-id="4f986-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="4f986-143">Q # innehåller metoder för att automatiskt generera en kontrollerad version av en åtgärd, vilket sparar programmerare från att behöva gå vidare till dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4f986-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="4f986-144">Ett exempel på detta visas nedan:</span><span class="sxs-lookup"><span data-stu-id="4f986-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="4f986-145">Mått operator</span><span class="sxs-lookup"><span data-stu-id="4f986-145">Measurement operator</span></span>
<span data-ttu-id="4f986-146">Den återstående åtgärden att visualisera i krets diagram är mått.</span><span class="sxs-lookup"><span data-stu-id="4f986-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="4f986-147">Mätningen tar ett qubit register, mäter det och matar ut resultatet som klassisk information.</span><span class="sxs-lookup"><span data-stu-id="4f986-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="4f986-148">En mätnings åtgärd anges av en mätar symbol och fungerar alltid som indata för ett qubit-register (betecknas med en heldragen linje) och utvärderar klassisk information (betecknas med en dubbel linje).</span><span class="sxs-lookup"><span data-stu-id="4f986-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="4f986-149">Mer specifikt ser en sådan under krets ut så här:</span><span class="sxs-lookup"><span data-stu-id="4f986-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="4f986-150">![mätnings krets](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="4f986-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="4f986-151">Q # implementerar en [mått operator](xref:microsoft.quantum.primitive.measure) för det här ändamålet.</span><span class="sxs-lookup"><span data-stu-id="4f986-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="4f986-152">Mer information finns i [avsnittet om mått](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="4f986-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="4f986-153">På samma sätt är under kretsen</span><span class="sxs-lookup"><span data-stu-id="4f986-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="4f986-154">ger en klassisk kontrollerad grind där $G $ tillämpas på den klassiska kontroll biten som värde $1 $.</span><span class="sxs-lookup"><span data-stu-id="4f986-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="4f986-155">Diagram över Teleportion krets</span><span class="sxs-lookup"><span data-stu-id="4f986-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="4f986-156">[Quantum Teleportion](xref:microsoft.quantum.techniques.puttingittogether) är kanske den bästa Quantum-algoritmen för att illustrera dessa komponenter.</span><span class="sxs-lookup"><span data-stu-id="4f986-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="4f986-157">Quantum Teleportion är en metod för att flytta data i en Quantum-dator (eller till och med mellan avlägsen quantum datorer i ett Quantum-nätverk) genom användning av entanglement och mätning.</span><span class="sxs-lookup"><span data-stu-id="4f986-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="4f986-158">Det kan vara intressant att flytta ett Quantum-tillstånd, säga värdet i en specifik qubit, från en qubit till en annan, utan att ens veta vad qubit värde är!</span><span class="sxs-lookup"><span data-stu-id="4f986-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="4f986-159">Detta är nödvändigt för att protokollet ska fungera enligt lagstiftningen i Quantum Mechanics.</span><span class="sxs-lookup"><span data-stu-id="4f986-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="4f986-160">Den andra kretsen för Quantum Teleportion anges nedan. Vi tillhandahåller också en kommenterad version av kretsen för att illustrera hur du kan läsa Quantum-kretsen.</span><span class="sxs-lookup"><span data-stu-id="4f986-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
