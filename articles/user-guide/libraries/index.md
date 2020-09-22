---
title: Quantum Development Kit-bibliotek
description: Översikt över de standard-, kemi- och matematikbibliotek som ingår i Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835731"
---
# <a name="overview-of-no-locq-libraries"></a>Översikt av Q#-bibliotek
Det finns flera bibliotek som medföljer Quantum Development Kit och som gör det enklare att utveckla kvantprogram i Q#.
I det här avsnittet av dokumentationen beskriver vi dessa bibliotek och hur du använder dem i dina program.

- [**Standardbibliotek**](xref:microsoft.quantum.libraries.standard.intro): I det här avsnittet beskrivs inledningen, som definierar gränssnittet mellan Q#-program och måldatorer samt canon, ett Q#-bibliotek som tillhandahåller generella åtgärder och funktioner som används vid skrivandet av Q#-program.
- [**Bibliotek för kvantkemi**](xref:microsoft.quantum.chemistry.concepts.intro): Det här avsnittet beskriver kvantkemibiblioteket, som tillhandahåller en datamodell för inläsning av representationer av fermioniska hamiltonska värden samt åtgärder och funktioner för kvantsimulering som agerar på dessa representationer.
- [**Bibliotek för kvantmatematik**](xref:microsoft.quantum.numerics.intro): I det här avsnittet beskrivs biblioteket för kvantmatematik, som innehåller implementeringar för en mängd olika matematiska funktioner. Det stöder heltal (signerade och osignerade) samt representationer av fast punkt.
- [**Bibliotek för kvantmaskininlärning**](xref:microsoft.quantum.machine-learning.concepts.intro): I det här avsnittet beskrivs biblioteket för kvantmaskininlärning, som innehåller en implementering av de sekventiella klassificerare som använder kvantberäkning för att förstå data.

Bibliotekets källor samt kodexempel kan hämtas från GitHub.
Mer information finns i [Licensiering](xref:microsoft.quantum.libraries.licensing). Observera att det även finns paketreferenser (”binärfiler”) för biblioteken, vilket är ett annat sätt att inkludera biblioteken i projekt på.
Du kan enkelt hämta dem via [NuGet](https://nuget.org).
