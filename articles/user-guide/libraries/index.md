---
title: Quantum Development Kit-bibliotek
description: Översikt över de standard-, kemi- och matematikbibliotek som ingår i Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273882"
---
# <a name="overview-of-q-libraries"></a>Översikt över Q#-biblioteken
Det finns flera bibliotek som medföljer Quantum Development Kit och gör det enklare att utveckla kvantprogram i Q#.
I det här avsnittet av dokumentationen beskriver vi dessa bibliotek och hur du använder dem i dina program.

- [**Standardbibliotek**](xref:microsoft.quantum.libraries.standard.intro): I det här avsnittet beskrivs inledningen, som definierar gränssnittet mellan Q#-program och måldatorer samt Canon, ett Q#-bibliotek som tillhandahåller generella åtgärder och funktioner som används vid skrivandet av Q#-program.
- [**Bibliotek för kvantkemi**](xref:microsoft.quantum.chemistry.concepts.intro): Det här avsnittet beskriver kvantkemibiblioteket, som tillhandahåller en datamodell för inläsning av representationer av fermioniska hamiltonska värden samt åtgärder och funktioner för kvantsimulering som agerar på dessa representationer.
- [**Bibliotek för kvantmatematik**](xref:microsoft.quantum.numerics.intro): I det här avsnittet beskrivs biblioteket för kvantmatematik, som innehåller implementeringar för en mängd olika matematiska funktioner. Det stöder heltal (signerade och osignerade) samt representationer av fast punkt.

Bibliotekets källor samt kodexempel kan hämtas från GitHub. Mer information finns i [licensavsnittet](xref:microsoft.quantum.libraries.licensing). Observera att det även finns paketreferenser (”binärfiler”) för biblioteken, vilket är ett annat sätt att inkludera biblioteken i projekt. Du kan enkelt skaffa dem via [NuGet](https://nuget.org).
