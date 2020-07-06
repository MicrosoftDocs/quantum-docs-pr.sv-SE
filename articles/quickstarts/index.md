---
title: Installera Microsoft Quantum Development Kit (QDK)
description: Så här installerar du Microsoft Quantum Development Kit för olika miljöer.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: ee8d210d67a20cfea3bdc36162efc47f021a6dc6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885458"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installera Microsoft Quantum Development Kit (QDK)

Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering. QDK består av:

- Programmeringsspråket Q#
- En samling bibliotek som abstraherar komplexa funktioner i Q#
- API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#
- Verktyg som underlättar ditt utvecklingsarbete

Q#-program kan köras som fristående program med Visual Studio Code eller Visual Studio, eller genom Jupyter Notebooks med IQ# Jupyter-kärnan.
De kan också paras med ett värdprogram skrivet i ett .NET-språk (vanligtvis C#) eller Python, så att du kan anropa kvantåtgärder från ett klassiskt program.

Arbetsflödena för var och en av dessa installationer beskrivs och jämförs i [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs).

Om du vill fortsätta med att installera QDK och skapa Q#-projekt väljer du önskad installation:

[Utveckla med Q#-kommandoradsprogram](xref:microsoft.quantum.install.standalone) – välj den här metoden om du vill arbeta med Q# från kommandoraden. För detta krävs inte en drivrutin eller ett värdprogram som alternativen nedan.

[Utveckla med Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) – välj den här miljön om du vill köra Q#-kod i celler med inbäddad text eller skapa interaktiva självstudier om kvantberäkning. 

[Utveckla med Q# och Python](xref:microsoft.quantum.install.python) – gör att du kan kombinera Python och Q# för att skapa ett Python-värdprogram som anropar Q#-åtgärder.

[Utveckla med Q# och .NET](xref:microsoft.quantum.install.cs) – kombinera C#, F# eller VB.NET med Q# för att skapa ett .NET-värdprogram som anropar Q#-åtgärder.
