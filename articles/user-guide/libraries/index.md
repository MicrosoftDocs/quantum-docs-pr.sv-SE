---
title: Quantum Development Kit-bibliotek
description: Översikt över de standard-, kemi- och matematikbibliotek som ingår i Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: d61fe459362fdb5f3550768a26b34656a8a538a7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869111"
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
