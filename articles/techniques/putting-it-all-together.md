---
title: 'Q #-tekniker – placera allt tillsammans'
description: 'Gå igenom ett Basic Q #-program som visar Quantum Teleportion.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6c988f77ef6e433945dbf21dfb41204c74bdda3e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906839"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="ac2a0-103">Placera allt tillsammans: Teleportion</span><span class="sxs-lookup"><span data-stu-id="ac2a0-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="ac2a0-104">Vi går tillbaka till exemplet på den Teleportion-krets som definieras i [Quantum-kretsar](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="ac2a0-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="ac2a0-105">Vi ska använda det här för att illustrera de koncept vi har lärt dig hittills.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="ac2a0-106">En förklaring av Quantum Teleportion finns nedan för de som inte är bekanta med teori, följt av en genom gång av kod implementeringen i Q #.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="ac2a0-107">Quantum Teleportion: teori</span><span class="sxs-lookup"><span data-stu-id="ac2a0-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="ac2a0-108">Quantum Teleportion är en teknik för att skicka ett okänt Quantum-tillstånd (som vi refererar till som "__meddelande__") från en qubit på en plats till en qubit på en annan plats (vi kommer att se dessa qubits som "__här__" och "__där__").</span><span class="sxs-lookup"><span data-stu-id="ac2a0-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="ac2a0-109">Vi kan representera vårt __meddelande__ som en Vector med Dirac-notation:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="ac2a0-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="ac2a0-111">__Meddelandets__ qubit tillstånd är okänt för oss eftersom vi inte vet värdena för $ \alpha $ och $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="ac2a0-112">Steg 1: skapa ett Entangled-tillstånd</span><span class="sxs-lookup"><span data-stu-id="ac2a0-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="ac2a0-113">För att kunna skicka det __meddelande__ __som krävs för att qubit ska__ kunna Entangled med qubit __där__.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="ac2a0-114">Detta uppnås genom att använda en Hadamard-grind, följt av en CNOT-grind.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="ac2a0-115">Nu ska vi titta på det matematiska arbetet bakom dessa grind åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="ac2a0-116">Vi kommer att börja med qubits __här__ och __där__ både i $ \ket{0}$ State.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="ac2a0-117">När Entangling dessa qubits är de i ett tillstånd:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="ac2a0-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="ac2a0-119">Steg 2: skicka meddelandet</span><span class="sxs-lookup"><span data-stu-id="ac2a0-119">Step 2: Send the message</span></span>
<span data-ttu-id="ac2a0-120">För att skicka __meddelandet__ använder vi först en CNOT-port med __meddelandet__ qubit och __här__ qubit som indata ( __meddelandet__ qubit som kontrollen och __här__ qubit är mål-qubit, i den här instansen).</span><span class="sxs-lookup"><span data-stu-id="ac2a0-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="ac2a0-121">Det går att skriva till det här ingångs läget:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-121">This input state can be written:</span></span>

<span data-ttu-id="ac2a0-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="ac2a0-123">Detta utökar till:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-123">This expands to:</span></span>

<span data-ttu-id="ac2a0-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="ac2a0-125">Som en påminnelse vänder CNOT-grinden mål-qubit när kontroll-qubit är 1.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="ac2a0-126">Till exempel resulterar en inmatare på $ \ket{000}$ ingen ändring som den första qubit (kontrollen) är 0.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="ac2a0-127">Använd dock ett fall där den första qubit är 1 – till exempel en inmatad $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="ac2a0-128">I den här instansen är utdata $ \ket{110}$ som den andra qubit (målet) vändas av CNOT-porten.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="ac2a0-129">Nu ska vi ta med våra utdata när CNOT-porten har handlat på vår indata ovan.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="ac2a0-130">Resultatet är:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-130">The result is:</span></span>

<span data-ttu-id="ac2a0-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="ac2a0-132">Nästa steg för att skicka __meddelandet__ är att tillämpa en Hadamard-grind på __meddelandet__ qubit (det är den första qubit i varje term).</span><span class="sxs-lookup"><span data-stu-id="ac2a0-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="ac2a0-133">Som en påminnelse gör Hadamard-grinden följande:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="ac2a0-134">Indata</span><span class="sxs-lookup"><span data-stu-id="ac2a0-134">Input</span></span> | <span data-ttu-id="ac2a0-135">Resultat</span><span class="sxs-lookup"><span data-stu-id="ac2a0-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="ac2a0-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="ac2a0-136">$\ket{0}$</span></span>  | <span data-ttu-id="ac2a0-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="ac2a0-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="ac2a0-138">$\ket{1}$</span></span>  | <span data-ttu-id="ac2a0-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="ac2a0-140">Om vi tillämpar Hadamard-porten på den första qubit av varje term i våra utdata ovan får vi följande resultat:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="ac2a0-141">$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="ac2a0-142">Observera att varje term har $2 \frac{1}{\sqrt{2}} $ faktorer.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="ac2a0-143">Vi kan multiplicera dessa resultat genom att ge följande resultat:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="ac2a0-144">$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="ac2a0-145">$ \Frac{1}{2}$-faktorn är gemensam för varje term, så vi kan nu ta den utanför hakparenteserna:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="ac2a0-146">$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="ac2a0-147">Vi kan sedan multiplicera hakparenteserna för varje term som ger:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="ac2a0-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="ac2a0-149">Steg 3: mät resultatet</span><span class="sxs-lookup"><span data-stu-id="ac2a0-149">Step 3: Measure the result</span></span>

<span data-ttu-id="ac2a0-150">På grund av detta __och Entangled__ kommer eventuella mått för __detta__ att påverka status för __där__.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="ac2a0-151">Om vi mäter det första och andra qubit (__meddelande__ och __här__) kan vi lära sig det tillstånd som __finns__ i, på grund av den här egenskapen för entanglement.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="ac2a0-152">Om vi mäter och får resultat 00, komprimeras överplaceringen och endast de villkor som stämmer med det här resultatet lämnas.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ac2a0-153">Det är $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="ac2a0-154">Detta kan omanpassas till $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="ac2a0-155">Om vi mäter den första och andra qubit till 00, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="ac2a0-156">Om vi mäter och erhåller ett resultat 01, komprimeras överplaceringen och endast de villkor som stämmer med det här resultatet lämnas.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ac2a0-157">Det är $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="ac2a0-158">Detta kan omanpassas till $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="ac2a0-159">Om vi mäter den första och andra qubit till 01, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="ac2a0-160">Om vi mäter och erhåller ett resultat 10, komprimeras överplaceringen och endast de villkor som stämmer med det här resultatet.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ac2a0-161">Det är $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="ac2a0-162">Detta kan omanpassas till $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="ac2a0-163">Om vi mäter den första och andra qubit till 10, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="ac2a0-164">Om vi mäter och erhåller ett resultat 11, komprimeras överplaceringen och endast de villkor som är konsekventa med det här resultatet lämnas.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ac2a0-165">Det är $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="ac2a0-166">Detta kan omanpassas till $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="ac2a0-167">Om vi mäter den första och andra qubit till 11, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="ac2a0-168">Steg 4: tolka resultatet</span><span class="sxs-lookup"><span data-stu-id="ac2a0-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="ac2a0-169">Som en påminnelse skulle det ursprungliga __meddelandet__ som vi vill skicka var:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="ac2a0-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="ac2a0-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="ac2a0-171">Vi måste hämta __det__ qubit i det här läget, så att det mottagna läget är det som avsågs.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="ac2a0-172">Om vi mätte och fick resultatet 00 är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="ac2a0-173">Eftersom det här är det avsedda __meddelandet__krävs ingen ändring.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="ac2a0-174">Om vi mätte och fick resultatet 01, är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="ac2a0-175">Detta skiljer sig från det avsedda __meddelandet__, men att använda en icke-grind ger oss det önskade tillstånd $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="ac2a0-176">Om vi mätte och fick resultatet 10, är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="ac2a0-177">Detta skiljer sig från det avsedda __meddelandet__, men att använda en Z-grind ger oss det önskade läget $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="ac2a0-178">Om vi mätte och fick resultatet 11, är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="ac2a0-179">Detta skiljer sig från det avsedda __meddelandet__, men att använda en icke-grind följt av en Z-grind ger oss det önskade läget $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="ac2a0-180">Om vi mäter och det första qubit är 1, används en Z-grind för att sammanfatta.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="ac2a0-181">Om vi mäter och den andra qubit är 1, tillämpas en icke-grind.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="ac2a0-182">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="ac2a0-182">Summary</span></span>
<span data-ttu-id="ac2a0-183">Nedan visas en text boks Quantum-krets som implementerar Teleportion.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="ac2a0-184">Flytta från vänster till höger kan du se:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="ac2a0-185">Steg 1: Entangling __här__ och __där__ genom att tillämpa en Hadamard-grind och CNOT-grind.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="ac2a0-186">Steg 2: skicka __meddelandet__ med en CNOT-grind och en Hadamard-grind.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="ac2a0-187">Steg 3: ta en mätning av den första och andra qubits, ett __meddelande__ och __här__.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="ac2a0-188">Steg 4: tillämpa en NOT-grind eller en Z-grind, beroende på resultatet av måttet i steg 3.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' Teleport (MSG: qubit, där: qubit): enhet '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="ac2a0-190">Quantum Teleportion: kod</span><span class="sxs-lookup"><span data-stu-id="ac2a0-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="ac2a0-191">Vi har vår krets för Quantum Teleportion:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-191">We have our circuit for quantum teleportation:</span></span>

![' Teleport (MSG: qubit, där: qubit): enhet '](~/media/teleportation.svg)

<span data-ttu-id="ac2a0-193">Vi kan nu översätta vart och ett av stegen i den här Quantum-kretsen till Q #.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="ac2a0-194">Steg 0: definition</span><span class="sxs-lookup"><span data-stu-id="ac2a0-194">Step 0: Definition</span></span>
<span data-ttu-id="ac2a0-195">När vi utför Teleportion måste vi känna till det __meddelande__ vi vill skicka och var vi vill skicka det (__där__).</span><span class="sxs-lookup"><span data-stu-id="ac2a0-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="ac2a0-196">Därför börjar vi genom att definiera en ny Teleport-åtgärd som har två qubits som argument, `msg` och `there`:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="ac2a0-197">Vi måste också allokera en qubit `here` som vi uppnår med ett `using` block:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="ac2a0-198">Steg 1: skapa ett Entangled-tillstånd</span><span class="sxs-lookup"><span data-stu-id="ac2a0-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="ac2a0-199">Vi kan sedan skapa Entangled-paret mellan `here` och `there` med hjälp av @"microsoft.quantum.intrinsic.h" och @"microsoft.quantum.intrinsic.cnot" åtgärder:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="ac2a0-200">Steg 2: skicka meddelandet</span><span class="sxs-lookup"><span data-stu-id="ac2a0-200">Step 2: Send the message</span></span>
<span data-ttu-id="ac2a0-201">Vi använder sedan nästa $ \operatorname{CNOT} $ och $H $ Gates för att flytta vårt meddelande qubit:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="ac2a0-202">Steg 3 & 4: mäta och tolka resultatet</span><span class="sxs-lookup"><span data-stu-id="ac2a0-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="ac2a0-203">Slutligen använder vi @"microsoft.quantum.intrinsic.m" för att utföra mätningarna och utföra de åtgärder som krävs för att få önskat tillstånd, som betecknas med `if`-satser:</span><span class="sxs-lookup"><span data-stu-id="ac2a0-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="ac2a0-204">Detta slutför definitionen av vår Teleportion-operatör, så att vi kan frigöra `here`, avsluta bröd texten och avsluta åtgärden.</span><span class="sxs-lookup"><span data-stu-id="ac2a0-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
