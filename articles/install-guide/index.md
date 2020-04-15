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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installera Microsoft Quantum Development Kit (QDK)

Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering. QDK består av:

- programmeringsspråket Q#
- en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#
- API:er för Python- och .NET-språk (C#, F# och VB.NET) för att kunna köra kvantprogram som skrivits i Q#
- verktyg som underlättar ditt utvecklingsarbete

Q#-program är ofta kopplade till ett värdprogram som skrivits på ett .NET-språk (vanligtvis C#) eller Python. Detta innebär att vi kan anropa kvantåtgärder inifrån ett klassiskt program.
Dessutom innehåller QDK Q#-stöd för Jupyter Notebooks med IQ# Jupyter-kärnan.

QDK:n är tillgänglig för flera utvecklingsmiljöer. Välj önskad konfiguration i avsnitten nedan:

- [Installera Q# för C#:](xref:microsoft.quantum.install.cs) Välj den här miljön om du vill kombinera C# och Q# till att skapa ett C#-värdprogram som anropar Q#-åtgärder.
- [Installera Q# för Python:](xref:microsoft.quantum.install.python) Välj den här miljön om du vill kombinera Python och Q# till att skapa ett Python-värdprogram som anropar Q#-åtgärder.
- [Installera Q# för Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) Välj den här miljön om du vill köra Q#-kod i celler med inbäddad text, eller skapa interaktiva självstudier för kvantberäkning. Välj inte den här miljön om du vill kombinera Q# med ett externt klassiskt värdprogram.
