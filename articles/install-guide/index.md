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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installera Microsoft Quantum Development Kit (QDK)

Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering. QDK består av:

- programmeringsspråket Q#
- en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#
- API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#
- verktyg som underlättar ditt utvecklingsarbete

Q#-program är ofta kopplade till ett värdprogram som skrivits på ett .NET-språk (vanligtvis C#) eller Python. Detta innebär att vi kan anropa kvantåtgärder inifrån ett klassiskt program.
Dessutom innehåller QDK Q#-stöd för Jupyter Notebooks med IQ# Jupyter-kärnan.

QDK:n är tillgänglig för flera utvecklingsmiljöer. Välj önskad konfiguration i avsnitten nedan:

- [Q#-kommandoradsprogram:](xref:microsoft.quantum.install.standalone) välj den här metoden om du vill arbeta med Q# från kommandoraden. För detta krävs inte en drivrutin eller ett värdprogram som alternativen nedan.
- [Installera Q# för Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) Välj den här miljön om du vill köra Q#-kod i celler med inbäddad text, eller skapa interaktiva självstudier för kvantberäkning. 
- [Utveckla med Q# och Python:](xref:microsoft.quantum.install.python) Om du vill kombinera Python och Q# för att skapa ett Python-värdprogram som anropar Q#-åtgärder.
- [Utveckla med Q# och C# eller F#:](xref:microsoft.quantum.install.cs) Om du vill kombinera C# eller F# och Q# för att skapa ett .NET-värdprogram som anropar Q#-åtgärder.
