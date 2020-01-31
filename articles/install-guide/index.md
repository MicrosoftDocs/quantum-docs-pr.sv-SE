---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820716"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="46f32-102">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="46f32-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="46f32-103">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="46f32-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="46f32-104">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="46f32-104">The QDK consists of:</span></span>

- <span data-ttu-id="46f32-105">programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="46f32-105">the Q# programming language</span></span>
- <span data-ttu-id="46f32-106">en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="46f32-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="46f32-107">API:er för Python- och .NET-språk (exempelvis: C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="46f32-107">APIs for Python and .NET languages (i.e.: C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="46f32-108">verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="46f32-108">tools to facilitate your development</span></span>

<span data-ttu-id="46f32-109">Q#-program är ofta kopplade till ett värdprogram som skrivits på ett .NET-språk (vanligtvis C#) eller Python.</span><span class="sxs-lookup"><span data-stu-id="46f32-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="46f32-110">Detta innebär att vi kan anropa kvantåtgärder inifrån ett klassiskt program.</span><span class="sxs-lookup"><span data-stu-id="46f32-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="46f32-111">Dessutom innehåller QDK Q#-stöd för Jupyter Notebooks med IQ# Jupyter-kärnan.</span><span class="sxs-lookup"><span data-stu-id="46f32-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="46f32-112">QDK:n är tillgänglig för flera utvecklingsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="46f32-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="46f32-113">Välj önskad konfiguration i avsnitten nedan:</span><span class="sxs-lookup"><span data-stu-id="46f32-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="46f32-114">[Installera Q# för C#:](xref:microsoft.quantum.install.cs) Välj den här miljön om du vill kombinera C# och Q# till att skapa ett C#-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="46f32-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="46f32-115">[Installera Q# för Python:](xref:microsoft.quantum.install.python) Välj den här miljön om du vill kombinera Python och Q# till att skapa ett Python-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="46f32-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="46f32-116">[Installera Q# för Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) Välj den här miljön om du vill köra Q#-kod i celler med inbäddad text, eller skapa interaktiva självstudier för kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="46f32-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="46f32-117">Välj inte den här miljön om du vill kombinera Q# med ett externt klassiskt värdprogram.</span><span class="sxs-lookup"><span data-stu-id="46f32-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
