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
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Konfigurera Microsoft Quantum Development Kit (QDK)

Lär dig att konfigurera Microsoft Quantum Development Kit (QDK) för din miljö så att du kan komma igång med kvantprogrammering. QDK består av:

- Programmeringsspråket Q#
- En samling bibliotek som abstraherar komplexa funktioner i Q#
- API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#
- Verktyg som underlättar ditt utvecklingsarbete

Q#-program kan köras som fristående program med Visual Studio Code eller Visual Studio, genom Jupyter Notebooks med IQ# Jupyter-kärnan, eller kopplade till ett värdprogram i Python eller ett .NET-språk (C#, F#). Du kan även köra Q#-program online med [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) eller [Docker](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Alternativ för att konfigurera QDK

Du kan använda QDK på tre olika sätt:

- [Installera QDK lokalt](#install-the-qdk-locally)
- [Använda QDK online](#use-the-qdk-online)
- [Använda en QDK Docker-avbildning](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Installera QDK lokalt

Du kan utveckla Q#-kod i de flesta av dina favorit-IDE:er, samt integrera Q# med andra språk, som Python och .NET (C#, F#).

|&nbsp; | **VS Code<br>(2019 eller senare)**| **Visual Studio<br>(2019 eller senare)** | **Jupyter Notebook** | **Kommandorad**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**Operativsystem** |Windows, macOS, Linux |Endast Windows |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# fristående** |<br>[Installera](xref:microsoft.quantum.install.standalone) |<br> [Installera](xref:microsoft.quantum.install.standalone)  |<br> [Installera](xref:microsoft.quantum.install.jupyter) |<br>[Installera](xref:microsoft.quantum.install.standalone)|
|**Q# och Python** |[Installera](xref:microsoft.quantum.install.python) |[Installera](xref:microsoft.quantum.install.python) |[Installera](xref:microsoft.quantum.install.jupyter) |[Installera](xref:microsoft.quantum.install.python) |
|**Q# och .NET (C#, F#)**|[Installera](xref:microsoft.quantum.install.cs) |[Installera](xref:microsoft.quantum.install.cs)|&#10006; |[Installera](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a>Använda QDK online

Du kan även utveckla Q#-kod utan att installera något lokalt, med följande alternativ:

|Resurs|Fördelar|Begränsningar|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|En omfattande utvecklingsmiljö online  |Kräver en Azure-prenumeration och en plan |
|[**Binder**](xref:microsoft.quantum.install.binder) | Kostnadsfri Notebook online |Ingen persistens |

## <a name="use-the-qdk-with-docker"></a>Använd QDK med Docker

Du kan använda vår QDK Docker-avbildning i din lokala Docker-installation eller i molnet via en tjänst som stöder Docker-avbildningar, till exempel ACI.

Du kan ladda ner IQ# Docker-avbildningen från https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

Du kan även använda Docker med en Visual Studio Code-container för utveckling på distans för att snabbt definiera utvecklingsmiljöer. Mer information om VS Code-utvecklingscontainrar finns i https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Nästa steg

Arbetsflödena för var och en av dessa konfigurationer beskrivs och jämförs i [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs).
