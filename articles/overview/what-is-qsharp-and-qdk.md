---
title: Vad är programmeringsspråket Q# och QDK?
description: Lär dig mer om Microsoft Quantum Development Kit, programmeringsspråket Q# samt hur du kan skapa kvantprogram.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5db574b0380ffa1616cb3959d84925854df4e321
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863781"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a><span data-ttu-id="bc6ac-103">Vad är programmeringsspråket Q# och QDK?</span><span class="sxs-lookup"><span data-stu-id="bc6ac-103">What are the Q# programming language and QDK?</span></span>

<span data-ttu-id="bc6ac-104">Q# är Microsofts programmeringsspråk med öppen källkod för utveckling och körning av kvantalgoritmer.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-104">Q# is Microsoft’s open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="bc6ac-105">Det ingår i Quantum Development Kit (QDK), som innehåller [Q#-bibliotek](xref:microsoft.quantum.libraries), [kvantsimulatorer](xref:microsoft.quantum.machines), [tillägg för andra programmeringsmiljöer](xref:microsoft.quantum.install) och [API-dokumentation](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="bc6ac-105">It’s part of the Quantum Development Kit (QDK), which includes [Q# libraries](xref:microsoft.quantum.libraries), [quantum simulators](xref:microsoft.quantum.machines), [extensions for other programming environments](xref:microsoft.quantum.install), and [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span> <span data-ttu-id="bc6ac-106">Utöver standardbiblioteket för Q# innehåller QDK även biblioteken för kemi, maskininlärning och tal.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-106">In addition to the Standard Q# library, the QDK includes Chemistry, Machine Learning, and Numeric libraries.</span></span>

<span data-ttu-id="bc6ac-107">Som programmeringsspråk omfattar Q# välkända element från Python, C# och F#. Det stöder en grundläggande procedurmodell för skrivande av program med loopar, if/then-instruktioner och vanliga datatyper.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-107">As a programming language, Q# draws familiar elements from Python, C#, and F# and supports a basic procedural model for writing programs with loops, if/then statements, and common data types.</span></span> <span data-ttu-id="bc6ac-108">Det introducerar även nya kvantspecifika datastrukturer och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-108">It also introduces new quantum-specific data structures and operations.</span></span>

## <a name="what-can-i-do-with-the-qdk"></a><span data-ttu-id="bc6ac-109">Vad kan jag göra med QDK?</span><span class="sxs-lookup"><span data-stu-id="bc6ac-109">What can I do with the QDK?</span></span>

<span data-ttu-id="bc6ac-110">QDK är en komplett development kit för Q# som du kan använda med vanliga verktyg och språk för att utveckla kvantprogram som du kan köra i olika miljöer.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-110">The QDK is a full-featured development kit for Q# that you can use with common tools and languages to develop quantum applications that you can run in various environments.</span></span> <span data-ttu-id="bc6ac-111">Q#-program kan köras som ett konsolprogram, via Jupyter Notebooks eller med ett Python- eller .NET-värdprogram.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-111">Q# programs can run as a console application, through Jupyter Notebooks, or use a Python or .NET host program.</span></span>

### <a name="develop-in-common-tools-and-environments"></a><span data-ttu-id="bc6ac-112">Utveckla i vanliga verktyg och miljöer</span><span class="sxs-lookup"><span data-stu-id="bc6ac-112">Develop in common tools and environments</span></span>

<span data-ttu-id="bc6ac-113">Integrera din kvantutveckling med [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) och [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span><span class="sxs-lookup"><span data-stu-id="bc6ac-113">Integrate your quantum development with [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone), and [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span></span> <span data-ttu-id="bc6ac-114">Använd de inbyggda API:erna för att koppla ihop dina program med värdspråken [Python](xref:microsoft.quantum.install.python) och [.NET](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="bc6ac-114">Use the built-in APIs for pairing your programs with [Python](xref:microsoft.quantum.install.python) and [.NET](xref:microsoft.quantum.install.cs) host languages.</span></span>

### <a name="try-quantum-operations-and-domain-specific-libraries"></a><span data-ttu-id="bc6ac-115">Prova kvantåtgärder och domänspecifika bibliotek</span><span class="sxs-lookup"><span data-stu-id="bc6ac-115">Try quantum operations and domain-specific libraries</span></span>

<span data-ttu-id="bc6ac-116">Skriv och testa kvantalgoritmer för att utforska superposition, sammanflätning och andra kvantåtgärder.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-116">Write and test quantum algorithms to explore superposition, entanglement, and other quantum operations.</span></span> <span data-ttu-id="bc6ac-117">Med Q#-biblioteken kan du köra komplexa kvantåtgärder utan att behöva utforma åtgärder på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-117">The Q# libraries enable you to run complex quantum operations without having to design low-level operation sequences.</span></span>

### <a name="run-programs-in-simulators"></a><span data-ttu-id="bc6ac-118">Köra program i simulatorer</span><span class="sxs-lookup"><span data-stu-id="bc6ac-118">Run programs in simulators</span></span>

<span data-ttu-id="bc6ac-119">Kör kvantprogram i en kvantsimulator med fullständigt tillstånd eller en Toffoli-simulator med begränsat omfång, eller testa Q#-kod i olika resursberäknare.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-119">Run your quantum programs on a full-state quantum simulator, a limited-scope Toffoli simulator, or test your Q# code in different resource estimators.</span></span> 

## <a name="where-can-i-learn-more"></a><span data-ttu-id="bc6ac-120">Var hittar jag mer information?</span><span class="sxs-lookup"><span data-stu-id="bc6ac-120">Where can I learn more?</span></span>

|||
| ---- | ---- |
| <span data-ttu-id="bc6ac-121">**Kvantberäkning är nytt för mig**</span><span class="sxs-lookup"><span data-stu-id="bc6ac-121">**I'm new to quantum computing**</span></span> | <span data-ttu-id="bc6ac-122">Gå igenom några grunder inom kvantfysik och kvantberäkning i [Viktiga begrepp](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="bc6ac-122">Review some basics of quantum physics and quantum computing in [Key Concepts](xref:microsoft.quantum.overview.understanding).</span></span>|
| <span data-ttu-id="bc6ac-123">**Jag vill gå in närmare på språket Q#**</span><span class="sxs-lookup"><span data-stu-id="bc6ac-123">**I want to dive deeper into the Q# language**</span></span> | <span data-ttu-id="bc6ac-124">Utforska typer, uttryck, variabler och kvantprogramstrukturer i [användarhandboken för Q#](xref:microsoft.quantum.guide).</span><span class="sxs-lookup"><span data-stu-id="bc6ac-124">Explore types, expressions, variables, and quantum program structure in the [Q# User Guide](xref:microsoft.quantum.guide).</span></span>|
| <span data-ttu-id="bc6ac-125">**Jag vill bara börja skriva kvantprogram**</span><span class="sxs-lookup"><span data-stu-id="bc6ac-125">**I just want to start writing quantum programs**</span></span> | <span data-ttu-id="bc6ac-126">Konfigurera din Q#-miljö och börja skriva kvantprogram i [Snabbstarter](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="bc6ac-126">Set up your Q# environment and start writing quantum programs in [QuickStarts](xref:microsoft.quantum.install).</span></span>|

## <a name="how-does-no-locq-work"></a><span data-ttu-id="bc6ac-127">Hur fungerar Q#?</span><span class="sxs-lookup"><span data-stu-id="bc6ac-127">How does Q# work?</span></span>

<span data-ttu-id="bc6ac-128">Q#-program kan kompileras till ett fristående program eller anropas av ett värdprogram som är skrivet i antingen Python eller ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-128">A Q# program can compile into a standalone application or be called by a host program that is written either in Python or a .NET language.</span></span>

<span data-ttu-id="bc6ac-129">När du kompilerar och kör programmet skapar det en instans av kvantsimulatorn och skickar Q#-koden till den.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-129">When you compile and run the program, it creates an instance of the quantum simulator and passes the Q# code to it.</span></span> <span data-ttu-id="bc6ac-130">Simulatorn använder Q#-koden för att skapa kvantbitar (simuleringar av kvantpartiklar) och tillämpa transformeringar för att ändra deras tillstånd.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-130">The simulator uses the Q# code to create qubits (simulations of quantum particles) and apply transformations to modify their state.</span></span> <span data-ttu-id="bc6ac-131">Resultatet av kvantåtgärderna i simulatorn returneras sedan till programmet.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-131">The results of the quantum operations in the simulator are then returned to the program.</span></span>  

<span data-ttu-id="bc6ac-132">Isolering av Q#-koden i simulatorn ser till att algoritmerna följer kvantfysikens lagar och att de körs korrekt på kvantdatorer.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-132">Isolating the Q# code in the simulator ensures that the algorithms follow the laws of quantum physics and can run correctly on quantum computers.</span></span>

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a><span data-ttu-id="bc6ac-134">Hur använder jag QDK?</span><span class="sxs-lookup"><span data-stu-id="bc6ac-134">How do I use the QDK?</span></span>

<span data-ttu-id="bc6ac-135">Allt du behöver för att skriva och köra Q#-program, inklusive Q#-kompilatorn, Q#-bibliotek och kvantsimulatorerna, kan installeras och köras från din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-135">Everything you need to write and run Q# programs, including the Q# compiler, the Q# libraries, and the quantum simulators, can be installed and run from your local computer.</span></span> <span data-ttu-id="bc6ac-136">Så småningom kan du köra Q#-programmen via fjärranslutning på en riktig kvantdator, men till dess tillhandahåller de kvantsimulatorer som medföljer QDK noggranna och tillförlitliga resultat.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-136">Eventually you will be able to run your Q# programs remotely on an actual quantum computer, but until then the quantum simulators provided with the QDK provide accurate and reliable results.</span></span>

- <span data-ttu-id="bc6ac-137">Att utveckla [Q#-program](xref:microsoft.quantum.install.standalone) är det snabbaste sättet att komma igång.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-137">Developing [Q# applications](xref:microsoft.quantum.install.standalone) is the quickest way to get started.</span></span>

- <span data-ttu-id="bc6ac-138">Kör fristående [Jupyter Notebooks med IQ#](xref:microsoft.quantum.install.jupyter), ett Jupyter-tillägg för kompilering, simulering och visualisering av Q#-program.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-138">Run standalone [Jupyter Notebooks with IQ#](xref:microsoft.quantum.install.jupyter), a Jupyter extension for compiling, simulating, and visualizing Q# programs.</span></span>

- <span data-ttu-id="bc6ac-139">Om du är bekant med [Python](xref:microsoft.quantum.install.python) kan du använda det som en värdprogrammeringsplattform för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-139">If you are familiar with [Python](xref:microsoft.quantum.install.python), you can use it as a host programming platform to get started.</span></span> <span data-ttu-id="bc6ac-140">Python är populärt både bland både utvecklare, forskare och lärare.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-140">Python enjoys widespread use not only among developers, but also scientists, researchers and teachers.</span></span>

- <span data-ttu-id="bc6ac-141">Om du redan har erfarenhet av [C#, F# eller VB.NET](xref:microsoft.quantum.install.cs) och är bekant med utvecklingsmiljön i Visual Studio behöver du bara lägga till några tillägg i Visual Studio för att förbereda det för Q#.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-141">If you already have experience with [C#, F#, or VB.NET](xref:microsoft.quantum.install.cs) and are familiar with the Visual Studio development environment, there are just a few extensions you need to add to Visual Studio to prepare it for Q#.</span></span>  

## <a name="summary"></a><span data-ttu-id="bc6ac-142">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="bc6ac-142">Summary</span></span>

<span data-ttu-id="bc6ac-143">Q# är ett programmeringsspråk med öppen källkod för utveckling av kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-143">Q# is an open-source programming language for developing quantum programs.</span></span> <span data-ttu-id="bc6ac-144">Det innehåller bibliotek som du kan använda för att skapa komplexa kvantåtgärder samt kvantsimulatorer där du kan köra och testa dina program med korrekta resultat.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-144">It has libraries that let you create complex quantum operations, and quantum simulators to accurately run and test your programs.</span></span> <span data-ttu-id="bc6ac-145">Q#-program kan köras som fristående appar eller anropas från ett Python- eller .NET-värdprogram, och de kan skrivas, köras och testas från din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-145">Q# programs can run as standalone apps or be called from a Python or .NET host program, and can be written, run, and tested from your local computer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc6ac-146">Efterföljande moment</span><span class="sxs-lookup"><span data-stu-id="bc6ac-146">Next Steps</span></span>

[<span data-ttu-id="bc6ac-147">Linjär algebra för kvantberäkning</span><span class="sxs-lookup"><span data-stu-id="bc6ac-147">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)
