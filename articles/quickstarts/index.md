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
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228856"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="6c1f2-103">Konfigurera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="6c1f2-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="6c1f2-104">Lär dig att konfigurera Microsoft Quantum Development Kit (QDK) för din miljö så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="6c1f2-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="6c1f2-105">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="6c1f2-105">The QDK consists of:</span></span>

- <span data-ttu-id="6c1f2-106">Programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="6c1f2-106">The Q# programming language</span></span>
- <span data-ttu-id="6c1f2-107">En samling bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="6c1f2-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="6c1f2-108">API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="6c1f2-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="6c1f2-109">Verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="6c1f2-109">Tools to facilitate your development</span></span>

<span data-ttu-id="6c1f2-110">Q#-program kan köras som fristående program med Visual Studio Code eller Visual Studio, genom Jupyter Notebooks med IQ# Jupyter-kärnan, eller kopplade till ett värdprogram i Python eller ett .NET-språk (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="6c1f2-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="6c1f2-111">Du kan även köra Q#-program online med [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) eller [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="6c1f2-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="6c1f2-112">Alternativ för att konfigurera QDK</span><span class="sxs-lookup"><span data-stu-id="6c1f2-112">Options for setting up the QDK</span></span>

<span data-ttu-id="6c1f2-113">Du kan använda QDK på tre olika sätt:</span><span class="sxs-lookup"><span data-stu-id="6c1f2-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="6c1f2-114">Installera QDK lokalt</span><span class="sxs-lookup"><span data-stu-id="6c1f2-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="6c1f2-115">Använda QDK online</span><span class="sxs-lookup"><span data-stu-id="6c1f2-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="6c1f2-116">Använda en QDK Docker-avbildning</span><span class="sxs-lookup"><span data-stu-id="6c1f2-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="6c1f2-117">Installera QDK lokalt</span><span class="sxs-lookup"><span data-stu-id="6c1f2-117">Install the QDK locally</span></span>

<span data-ttu-id="6c1f2-118">Du kan utveckla Q#-kod i de flesta av dina favorit-IDE:er, samt integrera Q# med andra språk, som Python och .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="6c1f2-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="6c1f2-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="6c1f2-119"><b>VS Code</span></span><br><span data-ttu-id="6c1f2-120">(2019 eller senare)</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="6c1f2-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6c1f2-121"><b>Visual Studio</span></span><br><span data-ttu-id="6c1f2-122">(2019 eller senare)</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="6c1f2-123"><b>Jupyter Notebook</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="6c1f2-124"><b>Kommandorad</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="6c1f2-125"><b>Stöd för operativsystem:</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="6c1f2-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-127">Endast Windows</span><span class="sxs-lookup"><span data-stu-id="6c1f2-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="6c1f2-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="6c1f2-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="6c1f2-130"><b>Q# fristående</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-131"><a href="xref:microsoft.quantum.install.standalone">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-132"><a href="xref:microsoft.quantum.install.standalone">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-133"><a href="xref:microsoft.quantum.install.jupyter">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-134"><a href="xref:microsoft.quantum.install.standalone">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="6c1f2-135"><b>Q# och Python</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-136"><a href="xref:microsoft.quantum.install.python">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-137"><a href="xref:microsoft.quantum.install.python">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-138"><a href="xref:microsoft.quantum.install.python">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-139"><a href="xref:microsoft.quantum.install.python">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="6c1f2-140"><b>Q# och .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="6c1f2-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="6c1f2-141"><a href="xref:microsoft.quantum.install.cs">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-142"><a href="xref:microsoft.quantum.install.cs">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="6c1f2-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="6c1f2-144"><a href="xref:microsoft.quantum.install.cs">Installera</a></span><span class="sxs-lookup"><span data-stu-id="6c1f2-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="6c1f2-145">Använda QDK online</span><span class="sxs-lookup"><span data-stu-id="6c1f2-145">Use the QDK Online</span></span>

<span data-ttu-id="6c1f2-146">Du kan även utveckla Q#-kod utan att installera något lokalt, med följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="6c1f2-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="6c1f2-147">Resurs</span><span class="sxs-lookup"><span data-stu-id="6c1f2-147">Resource</span></span>|<span data-ttu-id="6c1f2-148">Fördelar</span><span class="sxs-lookup"><span data-stu-id="6c1f2-148">Advantages</span></span>|<span data-ttu-id="6c1f2-149">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="6c1f2-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="6c1f2-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="6c1f2-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="6c1f2-151">En omfattande utvecklingsmiljö online</span><span class="sxs-lookup"><span data-stu-id="6c1f2-151">A rich online development environment</span></span>  |<span data-ttu-id="6c1f2-152">Kräver en Azure-prenumeration och en plan</span><span class="sxs-lookup"><span data-stu-id="6c1f2-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="6c1f2-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="6c1f2-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="6c1f2-154">Kostnadsfri Notebook online</span><span class="sxs-lookup"><span data-stu-id="6c1f2-154">Free online notebook experience</span></span> |<span data-ttu-id="6c1f2-155">Ingen persistens</span><span class="sxs-lookup"><span data-stu-id="6c1f2-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="6c1f2-156">Använd QDK med Docker</span><span class="sxs-lookup"><span data-stu-id="6c1f2-156">Use the QDK with Docker</span></span>

<span data-ttu-id="6c1f2-157">Du kan använda vår QDK Docker-avbildning i din lokala Docker-installation eller i molnet via en tjänst som stöder Docker-avbildningar, till exempel ACI.</span><span class="sxs-lookup"><span data-stu-id="6c1f2-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="6c1f2-158">Du kan ladda ner IQ# Docker-avbildningen från https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="6c1f2-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="6c1f2-159">Du kan även använda Docker med en Visual Studio Code-container för utveckling på distans för att snabbt definiera utvecklingsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="6c1f2-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="6c1f2-160">Mer information om VS Code-utvecklingscontainrar finns i https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="6c1f2-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c1f2-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6c1f2-161">Next steps</span></span>

<span data-ttu-id="6c1f2-162">Arbetsflödena för var och en av dessa konfigurationer beskrivs och jämförs i [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="6c1f2-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
