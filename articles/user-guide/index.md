---
title: Användarhandboken för Q#
description: Översikt över användarhandbokens syfte och innehåll
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771384"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="216ea-103">Användarhandboken för Q#</span><span class="sxs-lookup"><span data-stu-id="216ea-103">The Q# User Guide</span></span>

<span data-ttu-id="216ea-104">Välkommen till användarhandboken för Q#!</span><span class="sxs-lookup"><span data-stu-id="216ea-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="216ea-105">I de olika ämnena i den här guiden går vi igenom huvudbegreppen i språket Q#. Du får all information som du behöver för att skriva kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="216ea-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="216ea-106">Innehåll i användarhandboken</span><span class="sxs-lookup"><span data-stu-id="216ea-106">User Guide Contents</span></span>

- <span data-ttu-id="216ea-107">[Grunderna om Q#](xref:microsoft.quantum.guide.basics): En introduktionsöversikt om syftet med och funktionerna i programmeringsspråket Q#.</span><span class="sxs-lookup"><span data-stu-id="216ea-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="216ea-108">[Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs): beskriver hur ett Q#-program körs och ger en översikt av olika sätt att anropa programmet: från kommandoraden, i Q#-Jupyter Notebooks eller från ett klassiskt värdprogram som skrivits i Python eller ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="216ea-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="216ea-109">Språket Q#</span><span class="sxs-lookup"><span data-stu-id="216ea-109">Q# Language</span></span>

- <span data-ttu-id="216ea-110">[Typer i Q#](xref:microsoft.quantum.guide.types): Beskriver typmodellen i Q# och den syntax som används för att ange och arbeta med typer.</span><span class="sxs-lookup"><span data-stu-id="216ea-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="216ea-111">[Typuttryck](xref:microsoft.quantum.guide.expressions): Beskriver hur du anger, refererar till, kombinerar och arbetar med värden för varje typ i Q#.</span><span class="sxs-lookup"><span data-stu-id="216ea-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="216ea-112">Använda Q#</span><span class="sxs-lookup"><span data-stu-id="216ea-112">Using Q#</span></span>

- <span data-ttu-id="216ea-113">[Filstruktur för Q#](xref:microsoft.quantum.guide.filestructure): Beskriver strukturen och syntaxen för en `*.qs` Q#-fil.</span><span class="sxs-lookup"><span data-stu-id="216ea-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="216ea-114">[Åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions): Beskriver de två anropningsbara typerna i språket Q#: *åtgärder*, som används för åtgärder med kvantbitsregister, samt *funktioner*, som enbart används med klassisk information.</span><span class="sxs-lookup"><span data-stu-id="216ea-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="216ea-115">Här kan du se hur du definierar och anropar dem, inklusive relaterade och kontrollerade versioner av kvantåtgärder.</span><span class="sxs-lookup"><span data-stu-id="216ea-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="216ea-116">[Variabler](xref:microsoft.quantum.guide.variables): Beskriver variablernas roll i Q#-program och hur du använder dem på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="216ea-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="216ea-117">Du hittar till exempel information om bindande omfång och om skillnaden mellan oföränderliga och föränderliga variabler och hur du tilldelar eller omtilldelar dem.</span><span class="sxs-lookup"><span data-stu-id="216ea-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="216ea-118">[Arbeta med kvantbitar](xref:microsoft.quantum.guide.qubits): Beskriver de funktioner i Q# som används för enskilda kvantbitar och system med kvantbitar, mer specifikt hur du allokerar dem, utför åtgärder på dem och mäter dem.</span><span class="sxs-lookup"><span data-stu-id="216ea-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="216ea-119">[Kontrollflöde](xref:microsoft.quantum.guide.controlflow): Beskriver kontrollflödesmönstren för programmering i Q# som har stöd för många standardtekniker (till exempel villkorsstyrd bearbetning, *for*-loopar och *while*-loopar) samt det kvantspecifika *upprepa-tills-lyckas*-mönstret.</span><span class="sxs-lookup"><span data-stu-id="216ea-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional processing, *for* loops, *while* loops) as well as the quantum-specific *Repeat-Until-Success* pattern.</span></span>

- <span data-ttu-id="216ea-120">[Testa och felsöka](xref:microsoft.quantum.guide.testingdebugging): Beskriver några tekniker som du kan använda för att se till att koden gör det den ska göra.</span><span class="sxs-lookup"><span data-stu-id="216ea-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="216ea-121">På grund av den övergripande komplexiteten i kvantinformation, kan det krävas särskilda tekniker när kvantprogram ska felsökas.</span><span class="sxs-lookup"><span data-stu-id="216ea-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="216ea-122">Lyckligtvis stöder Q# många av de klassiska felsökningstekniker som programmerare är vana vid samt även dem som är kvantspecifika.</span><span class="sxs-lookup"><span data-stu-id="216ea-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="216ea-123">Dessa omfattar tekniker som att skapa och köra enhetstester i Q#, att bädda in *kontroller* för värden och sannolikheter i koden samt `Dump`-funktioner som visar måldatorernas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="216ea-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="216ea-124">Den senare kan användas tillsammans med vår simulator med fullständigt tillstånd för att felsöka särskilda delar av beräkningarna genom att kringgå vissa kvantbegränsningar, t.ex. [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="216ea-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="216ea-125">Kvantsimulatorer och resursberäknare</span><span class="sxs-lookup"><span data-stu-id="216ea-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="216ea-126">[Kvantsimulatorer och värdprogram](xref:microsoft.quantum.machines): En översikt av de olika tillgängliga simulatorerna samt hur värdprogram och måldatorer fungerar ihop för körning av Q#-program.</span><span class="sxs-lookup"><span data-stu-id="216ea-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="216ea-127">[Simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator): Måldatorn som simulerar det fullständiga kvanttillståndet.</span><span class="sxs-lookup"><span data-stu-id="216ea-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="216ea-128">Användbart för fullständig körning eller felsökning av program i mindre skala (mindre än ett dussintal kvantbitar)</span><span class="sxs-lookup"><span data-stu-id="216ea-128">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="216ea-129">[Resursberäknare](xref:microsoft.quantum.machines.resources-estimator): Beräknar de resurser som krävs för att köra en specifik instans av en Q#-åtgärd på en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="216ea-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="216ea-130">[Spårningssimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator. Det kan därför köra kvantprogram som använder tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="216ea-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="216ea-131">Användbart för felsökning av klassisk kod i ett kvantprogram, samt för att beräkna de resurser som krävs.</span><span class="sxs-lookup"><span data-stu-id="216ea-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="216ea-132">[Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator): En specialutvecklad kvantsimulator som kan användas med flera miljoner kvantbitar, men endast för program med en begränsad uppsättning kvantåtgärder – X, CNOT och multistyrd X.</span><span class="sxs-lookup"><span data-stu-id="216ea-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="216ea-133">Snabbreferenssidor</span><span class="sxs-lookup"><span data-stu-id="216ea-133">Quick Reference Pages</span></span>

- <span data-ttu-id="216ea-134">[Magiska IQ#-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp): Snabbreferenssida för magiska IQ#-kommandon i Q#-Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="216ea-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
