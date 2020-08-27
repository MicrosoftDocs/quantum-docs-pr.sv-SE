---
title: Installera Microsoft Quantum Development Kit (QDK)
description: Så här installerar du Microsoft Quantum Development Kit för olika miljöer.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863716"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="52f8e-103">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="52f8e-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="52f8e-104">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="52f8e-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="52f8e-105">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="52f8e-105">The QDK consists of:</span></span>

- <span data-ttu-id="52f8e-106">Programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="52f8e-106">The Q# programming language</span></span>
- <span data-ttu-id="52f8e-107">En samling bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="52f8e-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="52f8e-108">API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="52f8e-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="52f8e-109">Verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="52f8e-109">Tools to facilitate your development</span></span>

<span data-ttu-id="52f8e-110">Q#-program kan köras som fristående program med Visual Studio Code eller Visual Studio, eller genom Jupyter Notebooks med IQ# Jupyter-kärnan.</span><span class="sxs-lookup"><span data-stu-id="52f8e-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="52f8e-111">De kan också paras med ett värdprogram skrivet i ett .NET-språk (vanligtvis C#) eller Python, så att du kan anropa kvantåtgärder från ett klassiskt program.</span><span class="sxs-lookup"><span data-stu-id="52f8e-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="52f8e-112">Arbetsflödena för var och en av dessa konfigurationer beskrivs och jämförs i [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="52f8e-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="52f8e-113">Om du vill fortsätta med att installera QDK och skapa Q#-projekt väljer du önskad konfiguration:</span><span class="sxs-lookup"><span data-stu-id="52f8e-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="52f8e-114">[Utveckla med Q#-program](xref:microsoft.quantum.install.standalone) – välj den här metoden om du vill arbeta med Q# från kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="52f8e-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="52f8e-115">För detta krävs inte en drivrutin eller ett värdprogram som alternativen nedan.</span><span class="sxs-lookup"><span data-stu-id="52f8e-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="52f8e-116">[Utveckla med Q#-Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) – välj den här miljön om du vill köra Q#-kod i celler med inbäddad text eller skapa interaktiva självstudier om kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="52f8e-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="52f8e-117">[Utveckla med Q# och Python](xref:microsoft.quantum.install.python) – gör att du kan kombinera Python och Q# för att skapa ett Python-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="52f8e-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="52f8e-118">[Utveckla med Q# och .NET](xref:microsoft.quantum.install.cs) – kombinera C#, F# eller VB.NET med Q# för att skapa ett .NET-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="52f8e-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
