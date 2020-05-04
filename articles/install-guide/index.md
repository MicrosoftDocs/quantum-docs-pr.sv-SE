---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
description: Så här installerar du Microsoft Quantum Development Kit för C#-, Python- och Jupyter Notebook-miljöer.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680199"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="385f3-103">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="385f3-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="385f3-104">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="385f3-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="385f3-105">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="385f3-105">The QDK consists of:</span></span>

- <span data-ttu-id="385f3-106">programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="385f3-106">the Q# programming language</span></span>
- <span data-ttu-id="385f3-107">en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="385f3-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="385f3-108">API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="385f3-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="385f3-109">verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="385f3-109">tools to facilitate your development</span></span>

<span data-ttu-id="385f3-110">Q#-program är ofta kopplade till ett värdprogram som skrivits på ett .NET-språk (vanligtvis C#) eller Python.</span><span class="sxs-lookup"><span data-stu-id="385f3-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="385f3-111">Detta innebär att vi kan anropa kvantåtgärder inifrån ett klassiskt program.</span><span class="sxs-lookup"><span data-stu-id="385f3-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="385f3-112">Dessutom innehåller QDK Q#-stöd för Jupyter Notebooks med IQ# Jupyter-kärnan.</span><span class="sxs-lookup"><span data-stu-id="385f3-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="385f3-113">QDK:n är tillgänglig för flera utvecklingsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="385f3-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="385f3-114">Välj önskad konfiguration i avsnitten nedan:</span><span class="sxs-lookup"><span data-stu-id="385f3-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="385f3-115">[Q#-kommandoradsprogram:](xref:microsoft.quantum.install.standalone) välj den här metoden om du vill arbeta med Q# från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="385f3-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="385f3-116">För detta krävs inte en drivrutin eller ett värdprogram som alternativen nedan.</span><span class="sxs-lookup"><span data-stu-id="385f3-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="385f3-117">[Installera Q# för Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) Välj den här miljön om du vill köra Q#-kod i celler med inbäddad text, eller skapa interaktiva självstudier för kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="385f3-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="385f3-118">[Utveckla med Q# och Python:](xref:microsoft.quantum.install.python) Om du vill kombinera Python och Q# för att skapa ett Python-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="385f3-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="385f3-119">[Utveckla med Q# och C# eller F#:](xref:microsoft.quantum.install.cs) Om du vill kombinera C# eller F# och Q# för att skapa ett .NET-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="385f3-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
