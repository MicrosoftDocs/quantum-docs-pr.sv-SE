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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installera Microsoft Quantum Development Kit (QDK)

Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering. QDK består av:

- Programmeringsspråket Q#
- En samling bibliotek som abstraherar komplexa funktioner i Q#
- API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#
- Verktyg som underlättar ditt utvecklingsarbete

Q#-program kan köras som fristående program med Visual Studio Code eller Visual Studio, eller genom Jupyter Notebooks med IQ# Jupyter-kärnan.
De kan också paras med ett värdprogram skrivet i ett .NET-språk (vanligtvis C#) eller Python, så att du kan anropa kvantåtgärder från ett klassiskt program.

Arbetsflödena för var och en av dessa konfigurationer beskrivs och jämförs i [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs).

Om du vill fortsätta med att installera QDK och skapa Q#-projekt väljer du önskad konfiguration:

[Utveckla med Q#-program](xref:microsoft.quantum.install.standalone) – välj den här metoden om du vill arbeta med Q# från kommandotolken. För detta krävs inte en drivrutin eller ett värdprogram som alternativen nedan.

[Utveckla med Q#-Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) – välj den här miljön om du vill köra Q#-kod i celler med inbäddad text eller skapa interaktiva självstudier om kvantberäkning. 

[Utveckla med Q# och Python](xref:microsoft.quantum.install.python) – gör att du kan kombinera Python och Q# för att skapa ett Python-värdprogram som anropar Q#-åtgärder.

[Utveckla med Q# och .NET](xref:microsoft.quantum.install.cs) – kombinera C#, F# eller VB.NET med Q# för att skapa ett .NET-värdprogram som anropar Q#-åtgärder.
