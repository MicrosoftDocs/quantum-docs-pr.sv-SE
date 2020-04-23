---
title: 'Q # tekniker - Sätta ihop allt'
description: Gå igenom ett grundläggande Q# program som visar kvantteleportering.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030573"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="7e5f6-103">Sätta ihop allt: Teleportering</span><span class="sxs-lookup"><span data-stu-id="7e5f6-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="7e5f6-104">Låt oss återgå till exemplet med teleporteringskretsen som definieras i [Kvantkretsar](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="7e5f6-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="7e5f6-105">Vi ska använda detta för att illustrera de begrepp vi har lärt oss hittills.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="7e5f6-106">En förklaring av kvantteleportering ges nedan för dem som är obekanta med teorin, följt av en genomgång av koden genomförandet i Q # .</span><span class="sxs-lookup"><span data-stu-id="7e5f6-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="7e5f6-107">Quantum Teleportation: Teori</span><span class="sxs-lookup"><span data-stu-id="7e5f6-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="7e5f6-108">Quantum teleportering är en teknik för att skicka ett okänt kvanttillstånd (som vi kommer att hänvisa till som "__meddelande__" ) från en qubit på en plats till en qubit på en annan plats (vi hänvisar till dessa qubits som "__här__" och "__där__", respektive).</span><span class="sxs-lookup"><span data-stu-id="7e5f6-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="7e5f6-109">Vi kan representera vårt __budskap__ som en vektor med Dirac notation:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="7e5f6-110">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="7e5f6-111">__Meddelandet__ qubit tillstånd är okänd för oss eftersom vi inte vet värdena för $\alpha$ och $\beta$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="7e5f6-112">Steg 1: Skapa ett insnärjt tillstånd</span><span class="sxs-lookup"><span data-stu-id="7e5f6-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="7e5f6-113">För att skicka __meddelandet__ behöver vi för qubit __här__ att trasslad med qubit __där__.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="7e5f6-114">Detta uppnås genom att tillämpa en Hadamard gate, följt av en CNOT gate.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="7e5f6-115">Låt oss titta på matten bakom gate operationer.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="7e5f6-116">Vi börjar med qubits __här__ och __där__ både{0}i $ \ ket $ staten.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="7e5f6-117">Efter att ha trasslar in dessa qubits, är de i staten:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="7e5f6-118">$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="7e5f6-119">Steg 2: Skicka meddelandet</span><span class="sxs-lookup"><span data-stu-id="7e5f6-119">Step 2: Send the message</span></span>
<span data-ttu-id="7e5f6-120">För att skicka __meddelandet__ tillämpar vi först en CNOT-port med __meddelandet__ qubit och __här__ qubit som ingångar __(meddelandet__ qubit är kontrollen och __här__ qubit är målet qubit, i detta fall).</span><span class="sxs-lookup"><span data-stu-id="7e5f6-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="7e5f6-121">Det här indatatillståndet kan skrivas:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-121">This input state can be written:</span></span>

<span data-ttu-id="7e5f6-122">$$ \ket{\psi}\ket{\phi^+}{0} = (\alpha\ket +{1}\beta\ket{1})(\frac{2}{\sqrt }(\ket{00} + \ket{11})) $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="7e5f6-123">Detta utökas till:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-123">This expands to:</span></span>

<span data-ttu-id="7e5f6-124">$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} +{2}\frac{\beta}{\\sqrt }\ket{111} $$ $</span><span class="sxs-lookup"><span data-stu-id="7e5f6-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="7e5f6-125">Som en påminnelse vänder CNOT-porten målsansen när kontrolls qubit är 1.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="7e5f6-126">Så till exempel kommer en inmatning av $\ket{000}$ resultera i någon förändring eftersom den första qubit (kontrollen) är 0.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="7e5f6-127">Men ta ett fall där den första qubit är 1 -{100}till exempel en ingång på $\ket $.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="7e5f6-128">I det här fallet är utdata $\ket{110}$ som den andra qubit (målet) vänds av CNOT gate.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="7e5f6-129">Låt oss nu överväga vår produktion när CNOT gate har agerat på våra synpunkter ovan.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="7e5f6-130">Resultatet är:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-130">The result is:</span></span>

<span data-ttu-id="7e5f6-131">{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="7e5f6-132">Nästa steg för att skicka __meddelandet__ är att tillämpa en Hadamard-port på __meddelandet__ qubit (det är den första qubit av varje term).</span><span class="sxs-lookup"><span data-stu-id="7e5f6-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="7e5f6-133">Som en påminnelse gör Hadamard-porten följande:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="7e5f6-134">Indata</span><span class="sxs-lookup"><span data-stu-id="7e5f6-134">Input</span></span> | <span data-ttu-id="7e5f6-135">Resultat</span><span class="sxs-lookup"><span data-stu-id="7e5f6-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="7e5f6-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-136">$\ket{0}$</span></span>  | <span data-ttu-id="7e5f6-137">$\frac{1}{\sqrt{2}}(\ket{0} +{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="7e5f6-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-138">$\ket{1}$</span></span>  | <span data-ttu-id="7e5f6-139">$\frac{1}{\sqrt{2}}(\ket{0} -{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="7e5f6-140">Om vi tillämpar Hadamard gate till den första qubit av varje term av vår produktion ovan, får vi följande resultat:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="7e5f6-141">$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}}(\ket{1}{00} {2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {0} + \ket ))\ket + \frac{\alpha}{\sqrt }(\frac {\sqrt }(\ket + \ket ))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket $ket $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="7e5f6-142">Observera att varje term har{1}två $\frac{2}{\sqrt }$ faktorer.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="7e5f6-143">Vi kan multiplicera dessa ger följande resultat:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="7e5f6-144">$$ \frac{\alpha}{2}(\ket{0} +{1}\ket{00} )\ket +{2}\frac{\alpha} (\ket{0} +{1}\ket)\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket - \ket\ket{0} {1}{01} $$ $</span><span class="sxs-lookup"><span data-stu-id="7e5f6-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="7e5f6-145">Den $ \{1}{2}frac $ faktor är gemensam för varje term så att vi nu kan ta det utanför parentes:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="7e5f6-146">$${1}{2}\frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket \ket{01}\big] $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="7e5f6-147">Vi kan sedan multiplicera ut parenteserna för varje term som ger:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="7e5f6-148">{1}{2}$$ \frac \big[\alpha\ket{000} + \alpha\ket{100} +{011} \alpha\ket{111} + \alpha\ket{010} + \beta\ket -{001} \beta\ket{101}{110} + \beta\ket - \beta\ket \big] $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="7e5f6-149">Steg 3: Mät resultatet</span><span class="sxs-lookup"><span data-stu-id="7e5f6-149">Step 3: Measure the result</span></span>

<span data-ttu-id="7e5f6-150">På grund av __här__ och __där__ är insnärjda, någon mätning på __här__ kommer att påverka tillståndet i __det__.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="7e5f6-151">Om vi mäter den första och andra qubit __(meddelande__ och __här)__ kan vi lära oss vilket tillstånd __det finns__ i, på grund av denna egenskap av trassel.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="7e5f6-152">Om vi mäter och får ett resultat 00 kollapsar superpositionen, vilket innebär att endast termer överensstämmer med detta resultat.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7e5f6-153">Det är $\alpha\ket{000} +\beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="7e5f6-154">Detta kan återfactoreras till $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="7e5f6-155">Därför om vi mäter den första och andra qubit vara 00, vet vi att den tredje qubit, det ,{1} __är__i staten $(\alpha\ket{0} +\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="7e5f6-156">Om vi mäter och får ett resultat 01 kollapsar superpositionen, vilket innebär att endast termer överensstämmer med detta resultat.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7e5f6-157">Det är $\alpha\ket{011} +\beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="7e5f6-158">Detta kan återfactoreras till $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="7e5f6-159">Därför om vi mäter den första och andra qubit vara 01, vet vi att den tredje qubit, det ,{0} __är__i staten $(\alpha\ket{1} +\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="7e5f6-160">Om vi mäter och får ett resultat 10 kollapsar superpositionen och lämnar endast termer som överensstämmer med detta resultat.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7e5f6-161">Det är $\alpha\ket{100} -\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="7e5f6-162">Detta kan återfactoreras till $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="7e5f6-163">Därför om vi mäter den första och andra qubit vara 10, vet vi att den tredje qubit, det ,{1} __är__i staten $(\alpha\ket{0} -\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="7e5f6-164">Om vi mäter och får ett resultat 11 kollapsar superpositionen och lämnar endast termer som överensstämmer med detta resultat.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7e5f6-165">Det är $\alpha\ket{111} -\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="7e5f6-166">Detta kan återfactoreras till $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="7e5f6-167">Därför om vi mäter den första och andra qubit vara 11, vet vi att den tredje qubit, det ,{0} __är__i staten $(\alpha\ket{1} -\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="7e5f6-168">Steg 4: Tolka resultatet</span><span class="sxs-lookup"><span data-stu-id="7e5f6-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="7e5f6-169">Som en påminnelse, det ursprungliga __meddelandet__ vi ville skicka var:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="7e5f6-170">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="7e5f6-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="7e5f6-171">Vi måste få __in det__ i detta tillstånd, så att den mottagna staten är den som var avsedd.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="7e5f6-172">Om vi mätte och fick ett resultat av 00, då den tredje qubit,{0} __det__, är i staten $(\alpha\ket +\beta\ket)$.{1}</span><span class="sxs-lookup"><span data-stu-id="7e5f6-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="7e5f6-173">Eftersom detta är det avsedda __meddelandet__krävs ingen ändring.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="7e5f6-174">Om vi mätte och fick ett resultat av 01, då den tredje qubit,{1} __det__, är i staten $(\alpha\ket +\beta\ket)$.{0}</span><span class="sxs-lookup"><span data-stu-id="7e5f6-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="7e5f6-175">Detta skiljer sig från det avsedda __meddelandet__, men tillämpa en INTE gate{0} ger oss önskat{1}tillstånd $(\alpha\ket +\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="7e5f6-176">Om vi mätte och fick ett resultat av 10, då den tredje qubit,{0} __det__, är i staten $(\alpha\ket -\beta\ket)$.{1}</span><span class="sxs-lookup"><span data-stu-id="7e5f6-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="7e5f6-177">Detta skiljer sig från det avsedda __meddelandet__, men tillämpa en Z gate{0} ger oss önskat{1}tillstånd $(\alpha\ket +\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="7e5f6-178">Om vi mätte och fick ett resultat av 11, då den tredje qubit,{1} __det__, är i staten $(\alpha\ket -\beta\ket)$.{0}</span><span class="sxs-lookup"><span data-stu-id="7e5f6-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="7e5f6-179">Detta skiljer sig från det avsedda __meddelandet__, men tillämpa en INTE gate följt av en{0} Z gate ger{1}oss önskat tillstånd $(\alpha\ket +\beta\ket)$.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="7e5f6-180">Sammanfattningsvis, om vi mäter och den första qubit är 1, appliceras en Z-port.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="7e5f6-181">Om vi mäter och den andra qubit är 1, en INTE gate tillämpas.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="7e5f6-182">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="7e5f6-182">Summary</span></span>
<span data-ttu-id="7e5f6-183">Nedan visas en textbokskrets som implementerar teleporteringen.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="7e5f6-184">Om du flyttar från vänster till höger kan du se:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="7e5f6-185">Steg 1: Entangling __här__ och __där__ genom att tillämpa en Hadamard gate och CNOT gate.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="7e5f6-186">Steg 2: Skicka __meddelandet__ med en CNOT-grind och en Hadamard-port.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="7e5f6-187">Steg 3: Med ett mått på den första och andra qubits, __meddelande__ och __här__.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="7e5f6-188">Steg 4: Applicera en NOT-grind eller en Z-grind, beroende på resultatet av mätningen i steg 3.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["Teleport(msg: Qubit, där: Qubit) : Enhet"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="7e5f6-190">Quantum Teleportering: Kod</span><span class="sxs-lookup"><span data-stu-id="7e5f6-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="7e5f6-191">Vi har vår krets för kvantteleportering:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-191">We have our circuit for quantum teleportation:</span></span>

!["Teleport(msg: Qubit, där: Qubit) : Enhet"](~/media/teleportation.svg)

<span data-ttu-id="7e5f6-193">Vi kan nu översätta vart och ett av stegen i denna kvantkrets till Q#.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="7e5f6-194">Steg 0: Definition</span><span class="sxs-lookup"><span data-stu-id="7e5f6-194">Step 0: Definition</span></span>
<span data-ttu-id="7e5f6-195">När vi utför teleportering, måste vi veta __det budskap__ vi vill skicka, och där vi vill skicka det __(där).__</span><span class="sxs-lookup"><span data-stu-id="7e5f6-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="7e5f6-196">Av denna anledning börjar vi med att definiera en ny Teleport operation `msg` `there`som ges två qubits som argument, och:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="7e5f6-197">Vi måste också fördela en `here` qubit som `using` vi uppnår med ett block:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="7e5f6-198">Steg 1: Skapa ett insnärjt tillstånd</span><span class="sxs-lookup"><span data-stu-id="7e5f6-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="7e5f6-199">Vi kan sedan skapa det insnärjda paret mellan `here` och `there` genom att använda @"microsoft.quantum.intrinsic.h" och @"microsoft.quantum.intrinsic.cnot" operationer:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="7e5f6-200">Steg 2: Skicka meddelandet</span><span class="sxs-lookup"><span data-stu-id="7e5f6-200">Step 2: Send the message</span></span>
<span data-ttu-id="7e5f6-201">Vi använder sedan nästa $\operatorname{CNOT}$ och $H $ grindar för att flytta vårt meddelande qubit:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="7e5f6-202">Steg 3 & 4: Mätning och tolkning av resultatet</span><span class="sxs-lookup"><span data-stu-id="7e5f6-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="7e5f6-203">Slutligen använder @"microsoft.quantum.intrinsic.m" vi för att utföra mätningarna och utföra nödvändiga gate operationer för `if` att få önskat tillstånd, som betecknas med uttalanden:</span><span class="sxs-lookup"><span data-stu-id="7e5f6-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="7e5f6-204">Steg 5: Starta om qubit-registret</span><span class="sxs-lookup"><span data-stu-id="7e5f6-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="7e5f6-205">I slutet av varje Q # operation måste vi låta qubits{0}i staten $ \ ket $.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="7e5f6-206">Vi kan @"microsoft.quantum.intrinsic.reset" använda för att starta om alla qubits till noll tillstånd och detta kommer att avsluta vår operation.</span><span class="sxs-lookup"><span data-stu-id="7e5f6-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


