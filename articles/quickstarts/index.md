---
title: Konfigurera Microsoft Quantum Development Kit (QDK)
description: Lär dig att konfigurera Microsoft Quantum Development Kit för olika miljöer.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834490"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="63f17-103">Konfigurera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="63f17-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="63f17-104">Lär dig att konfigurera Microsoft Quantum Development Kit (QDK) för din miljö så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="63f17-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="63f17-105">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="63f17-105">The QDK consists of:</span></span>

- <span data-ttu-id="63f17-106">Programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="63f17-106">The Q# programming language</span></span>
- <span data-ttu-id="63f17-107">En samling bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="63f17-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="63f17-108">API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="63f17-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="63f17-109">Verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="63f17-109">Tools to facilitate your development</span></span>

<span data-ttu-id="63f17-110">Q#-program kan köras som fristående program med Visual Studio Code eller Visual Studio, genom Jupyter Notebooks med IQ# Jupyter-kärnan, eller kopplade till ett värdprogram i Python eller ett .NET-språk (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="63f17-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="63f17-111">Du kan även köra Q#-program online med [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) eller [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="63f17-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="63f17-112">Alternativ för att konfigurera QDK</span><span class="sxs-lookup"><span data-stu-id="63f17-112">Options for setting up the QDK</span></span>

<span data-ttu-id="63f17-113">Du kan använda QDK på tre olika sätt:</span><span class="sxs-lookup"><span data-stu-id="63f17-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="63f17-114">Installera QDK lokalt</span><span class="sxs-lookup"><span data-stu-id="63f17-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="63f17-115">Använda QDK online</span><span class="sxs-lookup"><span data-stu-id="63f17-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="63f17-116">Använda en QDK Docker-avbildning</span><span class="sxs-lookup"><span data-stu-id="63f17-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="63f17-117">Installera QDK lokalt</span><span class="sxs-lookup"><span data-stu-id="63f17-117">Install the QDK locally</span></span>

<span data-ttu-id="63f17-118">Du kan utveckla Q#-kod i de flesta av dina favorit-IDE:er, samt integrera Q# med andra språk, som Python och .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="63f17-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="63f17-119">**VS Code<br>(2019 eller senare)**</span><span class="sxs-lookup"><span data-stu-id="63f17-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="63f17-120">**Visual Studio<br>(2019 eller senare)**</span><span class="sxs-lookup"><span data-stu-id="63f17-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="63f17-121">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="63f17-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="63f17-122">**Kommandorad**</span><span class="sxs-lookup"><span data-stu-id="63f17-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="63f17-123">**Operativsystem**</span><span class="sxs-lookup"><span data-stu-id="63f17-123">**OS**</span></span> |<span data-ttu-id="63f17-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="63f17-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="63f17-125">Endast Windows</span><span class="sxs-lookup"><span data-stu-id="63f17-125">Windows only</span></span> |<span data-ttu-id="63f17-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="63f17-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="63f17-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="63f17-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="63f17-128">**Q# fristående**</span><span class="sxs-lookup"><span data-stu-id="63f17-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="63f17-129">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="63f17-130">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="63f17-131">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="63f17-132">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="63f17-133">**Q# och Python**</span><span class="sxs-lookup"><span data-stu-id="63f17-133">**Q#  and Python**</span></span> |[<span data-ttu-id="63f17-134">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="63f17-135">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="63f17-136">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="63f17-137">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="63f17-138">**Q# och .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="63f17-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="63f17-139">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="63f17-140">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="63f17-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="63f17-141">&#10006;</span></span> |[<span data-ttu-id="63f17-142">Installera</span><span class="sxs-lookup"><span data-stu-id="63f17-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="63f17-143">Använda QDK online</span><span class="sxs-lookup"><span data-stu-id="63f17-143">Use the QDK Online</span></span>

<span data-ttu-id="63f17-144">Du kan även utveckla Q#-kod utan att installera något lokalt, med följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="63f17-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="63f17-145">Resurs</span><span class="sxs-lookup"><span data-stu-id="63f17-145">Resource</span></span>|<span data-ttu-id="63f17-146">Fördelar</span><span class="sxs-lookup"><span data-stu-id="63f17-146">Advantages</span></span>|<span data-ttu-id="63f17-147">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="63f17-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="63f17-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="63f17-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="63f17-149">En omfattande utvecklingsmiljö online</span><span class="sxs-lookup"><span data-stu-id="63f17-149">A rich online development environment</span></span>  |<span data-ttu-id="63f17-150">Kräver en Azure-prenumeration och en plan</span><span class="sxs-lookup"><span data-stu-id="63f17-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="63f17-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="63f17-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="63f17-152">Kostnadsfri Notebook online</span><span class="sxs-lookup"><span data-stu-id="63f17-152">Free online notebook experience</span></span> |<span data-ttu-id="63f17-153">Ingen persistens</span><span class="sxs-lookup"><span data-stu-id="63f17-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="63f17-154">Använd QDK med Docker</span><span class="sxs-lookup"><span data-stu-id="63f17-154">Use the QDK with Docker</span></span>

<span data-ttu-id="63f17-155">Du kan använda vår QDK Docker-avbildning i din lokala Docker-installation eller i molnet via en tjänst som stöder Docker-avbildningar, till exempel ACI.</span><span class="sxs-lookup"><span data-stu-id="63f17-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="63f17-156">Du kan ladda ner IQ# Docker-avbildningen från https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="63f17-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="63f17-157">Du kan även använda Docker med en Visual Studio Code-container för utveckling på distans för att snabbt definiera utvecklingsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="63f17-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="63f17-158">Mer information om VS Code-utvecklingscontainrar finns i https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="63f17-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63f17-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="63f17-159">Next steps</span></span>

<span data-ttu-id="63f17-160">Arbetsflödena för var och en av dessa konfigurationer beskrivs och jämförs i [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="63f17-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
