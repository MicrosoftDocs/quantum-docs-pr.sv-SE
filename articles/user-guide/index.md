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
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231765"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="87460-103">Användarhandboken för Q#</span><span class="sxs-lookup"><span data-stu-id="87460-103">The Q# User Guide</span></span>

<span data-ttu-id="87460-104">Välkommen till användarhandboken för Q#!</span><span class="sxs-lookup"><span data-stu-id="87460-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="87460-105">I de olika avsnitten i den här vägledning introducerar vi några av grunderna för att utveckla kvantumprogram med hjälp av Q#.</span><span class="sxs-lookup"><span data-stu-id="87460-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="87460-106">Vi refererar till [vägledningen om Q#-språket](xref:microsoft.quantum.qsharp.index) för en fullständig specifikation och dokumentation av Q#-kvantprogrammeringsspråket.</span><span class="sxs-lookup"><span data-stu-id="87460-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="87460-107">Innehåll i användarhandboken</span><span class="sxs-lookup"><span data-stu-id="87460-107">User Guide Contents</span></span>

- <span data-ttu-id="87460-108">[Q# program](xref:microsoft.quantum.guide.programs): En snabb introduktion till kvantumprogram i Q#.</span><span class="sxs-lookup"><span data-stu-id="87460-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="87460-109">[Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs): beskriver hur ett Q#-program körs och ger en översikt av olika sätt att anropa programmet: från kommandoraden, i Q#-Jupyter Notebooks eller från ett klassiskt värdprogram som skrivits i Python eller ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="87460-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="87460-110">[Testa och felsöka](xref:microsoft.quantum.guide.testingdebugging): Beskriver några tekniker som du kan använda för att se till att koden gör det den ska göra.</span><span class="sxs-lookup"><span data-stu-id="87460-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="87460-111">På grund av den övergripande komplexiteten i kvantinformation, kan det krävas särskilda tekniker när kvantprogram ska felsökas.</span><span class="sxs-lookup"><span data-stu-id="87460-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="87460-112">Lyckligtvis stöder Q# många av de klassiska felsökningstekniker som programmerare är vana vid samt även dem som är kvantspecifika.</span><span class="sxs-lookup"><span data-stu-id="87460-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="87460-113">Dessa omfattar tekniker som att skapa och köra enhetstester i Q#, att bädda in *kontroller* för värden och sannolikheter i koden samt `Dump`-funktioner som visar måldatorernas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="87460-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="87460-114">Den senare kan användas tillsammans med vår simulator med fullständigt tillstånd för att felsöka särskilda delar av beräkningarna genom att kringgå vissa kvantbegränsningar, t.ex. [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="87460-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="87460-115">Kvantsimulatorer och resursberäknare</span><span class="sxs-lookup"><span data-stu-id="87460-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="87460-116">[Kvantsimulatorer och värdprogram](xref:microsoft.quantum.machines): En översikt av de olika tillgängliga simulatorerna samt hur värdprogram och måldatorer fungerar ihop för körning av Q#-program.</span><span class="sxs-lookup"><span data-stu-id="87460-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="87460-117">[Simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator): Måldatorn som simulerar det fullständiga kvanttillståndet.</span><span class="sxs-lookup"><span data-stu-id="87460-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="87460-118">Användbart för fullständig körning eller felsökning av program i mindre skala (mindre än ett dussintal kvantbitar)</span><span class="sxs-lookup"><span data-stu-id="87460-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="87460-119">[Resursberäknare](xref:microsoft.quantum.machines.resources-estimator): Beräknar de resurser som krävs för att köra en specifik instans av en Q#-åtgärd på en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="87460-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="87460-120">[Spårningssimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator. Det kan därför köra kvantprogram som använder tusentals kvantbitar.</span><span class="sxs-lookup"><span data-stu-id="87460-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="87460-121">Användbart för felsökning av klassisk kod i ett kvantprogram, samt för att beräkna de resurser som krävs.</span><span class="sxs-lookup"><span data-stu-id="87460-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="87460-122">[Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator): En specialutvecklad kvantsimulator som kan användas med flera miljoner kvantbitar, men endast för program med en begränsad uppsättning kvantåtgärder – X, CNOT och multistyrd X.</span><span class="sxs-lookup"><span data-stu-id="87460-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="87460-123">Snabbreferenssidor</span><span class="sxs-lookup"><span data-stu-id="87460-123">Quick Reference Pages</span></span>

- <span data-ttu-id="87460-124">[Magiska IQ#-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp): Snabbreferenssida för magiska IQ#-kommandon i Q#-Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="87460-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
