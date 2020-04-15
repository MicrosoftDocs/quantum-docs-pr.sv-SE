---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
description: Så här installerar du Microsoft Quantum Development Kit för C#-, Python- och Jupyter Notebook-miljöer.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 5fafb736f34d27f9233370a0a8a66c0613606048
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "77904782"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b087c-103">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b087c-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b087c-104">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="b087c-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="b087c-105">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="b087c-105">The QDK consists of:</span></span>

- <span data-ttu-id="b087c-106">programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="b087c-106">the Q# programming language</span></span>
- <span data-ttu-id="b087c-107">en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="b087c-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="b087c-108">API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="b087c-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="b087c-109">verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="b087c-109">tools to facilitate your development</span></span>

<span data-ttu-id="b087c-110">Q#-program är ofta kopplade till ett värdprogram som skrivits på ett .NET-språk (vanligtvis C#) eller Python.</span><span class="sxs-lookup"><span data-stu-id="b087c-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="b087c-111">Detta innebär att vi kan anropa kvantåtgärder inifrån ett klassiskt program.</span><span class="sxs-lookup"><span data-stu-id="b087c-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="b087c-112">Dessutom innehåller QDK Q#-stöd för Jupyter Notebooks med IQ# Jupyter-kärnan.</span><span class="sxs-lookup"><span data-stu-id="b087c-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="b087c-113">QDK:n är tillgänglig för flera utvecklingsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="b087c-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="b087c-114">Välj önskad konfiguration i avsnitten nedan:</span><span class="sxs-lookup"><span data-stu-id="b087c-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="b087c-115">[Installera Q# för C#:](xref:microsoft.quantum.install.cs) Välj den här miljön om du vill kombinera C# och Q# till att skapa ett C#-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b087c-115">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="b087c-116">[Installera Q# för Python:](xref:microsoft.quantum.install.python) Välj den här miljön om du vill kombinera Python och Q# till att skapa ett Python-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b087c-116">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="b087c-117">[Installera Q# för Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) Välj den här miljön om du vill köra Q#-kod i celler med inbäddad text, eller skapa interaktiva självstudier för kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="b087c-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="b087c-118">Välj inte den här miljön om du vill kombinera Q# med ett externt klassiskt värdprogram.</span><span class="sxs-lookup"><span data-stu-id="b087c-118">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
