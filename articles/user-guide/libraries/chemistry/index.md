---
title: Introduktion till kvantkemibiblioteket
description: Lär dig mer om Microsofts kvantkemibibliotek och hur det används för att simulera elektroniska strukturproblem på kvantdatorer.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15439a34933bd561dc011acf48e669abeb031e33
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835799"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introduktion till kvantkemibiblioteket

Simulering av fysiska system har länge spelat en central roll inom kvantberäkning.  Det beror på att många anser att simulering av kvantdynamik på kvantdatorer inte är gångbart eftersom komplexiteten hos dessa simuleringar ökar exponentiellt med storleken på det kvantsystem som ska simuleras.  Simulering av problem inom kemi och materialvetenskap är kanske den mest intressanta tillämpningen av kvantberäkning. Sådan skulle göra att vi kan undersöka mekanismer bakom kemiska reaktioner som hittills inte har kunnat mätas eller simuleras.  Det skulle även göra att vi kan simulera korrelerade elektroniska material, till exempel supraledare som fungerar vid höga temperaturer. Listan över tillämpningar i det här området är mycket omfattande.

Syftet med den här dokumentationen är att tillhandahålla en kortfattad introduktion till simulering av problem med elektronisk struktur i kvantdatorer i syfte att hjälpa läsaren att förstå den roll som många aspekter av biblioteket för simulering av hamiltonska värden spelar i det området.  Vi börjar med en kort introduktion till kvantmekanik och fortsätter sedan med en diskussion av hur elektroniska system modelleras i detta område.  Sedan går vi igenom hur kvantdynamik kan emuleras med hjälp av en kvantdator.  När detta är klart diskuterar vi två metoder som används för att sammanställa kvantdynamiken till sekvenser med elementära kretsar: Trotter-Suzuki-dekompositioner och qubitisering.
