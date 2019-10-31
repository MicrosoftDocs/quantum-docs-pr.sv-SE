---
title: Quantum Development Kit-bibliotek | Microsoft Docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 5a5b28f7e8c1669d26d1064753f20551a6b0d036
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2019
ms.locfileid: "72970396"
---
Det finns flera bibliotek som medföljer Quantum Development Kit och gör det enklare att utveckla kvantprogram i Q#.
I det här avsnittet av dokumentationen beskriver vi dessa bibliotek och hur du använder dem i dina program.

- [**Standardbibliotek**](xref:microsoft.quantum.libraries.standard.intro): I det här avsnittet beskrivs inledningen, som definierar gränssnittet mellan Q#-program och måldatorer samt Canon, ett Q#-bibliotek som tillhandahåller generella åtgärder och funktioner som används vid skrivandet av Q#-program.
- [**Bibliotek för kvantkemi**](xref:microsoft.quantum.chemistry.concepts.intro): Det här avsnittet beskriver kvantkemibiblioteket, som tillhandahåller en datamodell för inläsning av representationer av fermioniska hamiltonska värden samt åtgärder och funktioner för kvantsimulering som agerar på dessa representationer.
- [**Bibliotek för kvantmatematik**](xref:microsoft.quantum.numerics.intro): I det här avsnittet beskrivs biblioteket för kvantmatematik, som innehåller implementeringar för en mängd olika matematiska funktioner. Det stöder heltal (signerade och osignerade) samt representationer av fast punkt.

Bibliotekets källor samt kodexempel kan hämtas från GitHub. Mer information finns i [licensavsnittet](xref:microsoft.quantum.libraries.licensing). Observera att det även finns paketreferenser (”binärfiler”) för biblioteken, vilket är ett annat sätt att inkludera biblioteken i projekt. Du kan enkelt skaffa dem via [NuGet](https://nuget.org).  