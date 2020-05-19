---
title: Användarhandboken för Q#
description: Översikt över användarhandbokens syfte och innehåll
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430619"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="3c39d-103">Användarhandboken för Q#</span><span class="sxs-lookup"><span data-stu-id="3c39d-103">The Q# User Guide</span></span>

<span data-ttu-id="3c39d-104">Välkommen till användarhandboken för Q#!</span><span class="sxs-lookup"><span data-stu-id="3c39d-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="3c39d-105">Här går vi igenom huvudbegreppen i språket Q#, och du får all information som du behöver för att skriva kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="3c39d-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="3c39d-106">Innehåll i användarhandboken</span><span class="sxs-lookup"><span data-stu-id="3c39d-106">User Guide Contents</span></span>

- <span data-ttu-id="3c39d-107">[Grunderna i Q#](xref:microsoft.quantum.guide.basics): En introduktionsöversikt om syftet med och funktionerna i programmeringsspråket Q#.</span><span class="sxs-lookup"><span data-stu-id="3c39d-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="3c39d-108">Språket Q#</span><span class="sxs-lookup"><span data-stu-id="3c39d-108">Q# Language</span></span>

- <span data-ttu-id="3c39d-109">[Typer i Q#](xref:microsoft.quantum.guide.types): Beskriver typmodellen i Q# och syntaxen som används för att ange och arbeta med typer.</span><span class="sxs-lookup"><span data-stu-id="3c39d-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="3c39d-110">[Typuttryck](xref:microsoft.quantum.guide.expressions): Beskriver hur du anger, refererar till, kombinerar och arbetar med värden för varje typ i Q#.</span><span class="sxs-lookup"><span data-stu-id="3c39d-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="3c39d-111">Använda Q#</span><span class="sxs-lookup"><span data-stu-id="3c39d-111">Using Q#</span></span>

- <span data-ttu-id="3c39d-112">[Q#-filstruktur](xref:microsoft.quantum.guide.filestructure): Beskriver strukturen och syntaxen för en `*.qs`-Q#-fil.</span><span class="sxs-lookup"><span data-stu-id="3c39d-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="3c39d-113">[Åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions): Beskriver de två anropningsbara typerna i Q#-språket: *åtgärder*, som används för åtgärder med kvantbitsregister, samt *funktioner*, som enbart används med klassisk information.</span><span class="sxs-lookup"><span data-stu-id="3c39d-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="3c39d-114">Här kan du se hur du definierar och anropar dem, inklusive relaterade och kontrollerade versioner av kvantåtgärder.</span><span class="sxs-lookup"><span data-stu-id="3c39d-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="3c39d-115">[Variabler](xref:microsoft.quantum.guide.variables): Beskriver variablernas roll i Q#-program och hur du använder dem på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="3c39d-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="3c39d-116">Du hittar till exempel information om bindande omfång och om skillnaden mellan oföränderliga/föränderliga variabler och hur du tilldelar/omtilldelar dem.</span><span class="sxs-lookup"><span data-stu-id="3c39d-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="3c39d-117">[Arbeta med kvantbitar](xref:microsoft.quantum.guide.qubits): Beskriver de funktioner i Q# som används för enskilda kvantbitar och system med kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="3c39d-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="3c39d-118">Det innebär mer specifikt deras allokering, att utföra åtgärder på dem och slutligen deras mått.</span><span class="sxs-lookup"><span data-stu-id="3c39d-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="3c39d-119">[Kontrollflöde](xref:microsoft.quantum.guide.controlflow): Beskriver kontrollflödesmönstren för programmering i Q#, som har stöd för många standardtekniker (villkorlig körning, for-loopar, while-loopar osv.) samt det kvantspecifika ”upprepa-tills-lyckas”-mönstret.</span><span class="sxs-lookup"><span data-stu-id="3c39d-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="3c39d-120">[Testa och felsöka](xref:microsoft.quantum.guide.testingdebugging): Beskriver några tekniker som du kan använda för att se till att koden gör det den ska göra.</span><span class="sxs-lookup"><span data-stu-id="3c39d-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="3c39d-121">På grund av den övergripande komplexiteten i kvantinformation, kan det krävas särskilda tekniker när kvantprogram ska felsökas.</span><span class="sxs-lookup"><span data-stu-id="3c39d-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="3c39d-122">Lyckligtvis stöder Q# många av de klassiska felsökningstekniker som programmerare brukar använda, samt även de som är kvantspecifika.</span><span class="sxs-lookup"><span data-stu-id="3c39d-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="3c39d-123">Detta innefattar att skapa/köra enhetstester i Q#, bädda in *kontroller* av värden och sannolikheter i koden, samt `Dump`-funktioner som visar status för måldatorn.</span><span class="sxs-lookup"><span data-stu-id="3c39d-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="3c39d-124">Den senare kan användas tillsammans med vår simulator med fullständigt tillstånd för att felsöka särskilda delar av beräkningarna genom att kringgå vissa kvantbegränsningar (t.ex. ”no-cloning theorem”).</span><span class="sxs-lookup"><span data-stu-id="3c39d-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="3c39d-125">Kvantsimulatorer och resursberäknare</span><span class="sxs-lookup"><span data-stu-id="3c39d-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="3c39d-126">[Kvantsimulatorer och värdprogram](xref:microsoft.quantum.machines): En översikt över de olika tillgängliga simulatorerna, samt den generella modellen för körning mellan värdprogram och måldatorer.</span><span class="sxs-lookup"><span data-stu-id="3c39d-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="3c39d-127">[Simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator): Måldatorn som simulerar det fullständiga kvanttillståndet.</span><span class="sxs-lookup"><span data-stu-id="3c39d-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="3c39d-128">Användbart för fullständig körning eller felsökning av program i mindre skala (mindre än ett par dussin kvantbitar)</span><span class="sxs-lookup"><span data-stu-id="3c39d-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="3c39d-129">[Resursberäknare](xref:microsoft.quantum.machines.resources-estimator): Beräknar de resurser som krävs för att köra en specifik instans av en Q#-åtgärd på en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="3c39d-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="3c39d-130">[Spårningssimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator och kan därför köra kvantprogram som använder tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="3c39d-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="3c39d-131">Användbart för felsökning av klassisk kod i ett kvantprogram, samt för att beräkna de resurser som krävs.</span><span class="sxs-lookup"><span data-stu-id="3c39d-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="3c39d-132">[Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator): En specialutvecklad kvantsimulator som kan användas med flera miljoner kvantbitar, men endast för program med en begränsad uppsättning kvantåtgärder (närmare bestämt X, CNOT och multistyrd X).</span><span class="sxs-lookup"><span data-stu-id="3c39d-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="3c39d-133">Snabbreferenssidor</span><span class="sxs-lookup"><span data-stu-id="3c39d-133">Quick Reference Pages</span></span>

- <span data-ttu-id="3c39d-134">[Magiska kommandon för IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Snabbreferenssida för magiska kommandon för IQ# i Q# Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="3c39d-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
