---
title: Introduktion till kvantkemibiblioteket
description: Lär dig mer om Microsofts kvantkemibibliotek och hur det används för att simulera elektroniska strukturproblem på kvantdatorer.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: e2ec4173d4f2bdaac7125c13b09708934b758a1d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869417"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introduktion till kvantkemibiblioteket

Simulering av fysiska system har länge spelat en central roll inom kvantberäkning.  Det beror på att många anser att simulering av kvantdynamik på kvantdatorer inte är gångbart eftersom komplexiteten hos dessa simuleringar ökar exponentiellt med storleken på det kvantsystem som ska simuleras.  Simulering av problem inom kemi och materialvetenskap är kanske den mest intressanta tillämpningen av kvantberäkning. Sådan skulle göra att vi kan undersöka mekanismer bakom kemiska reaktioner som hittills inte har kunnat mätas eller simuleras.  Det skulle även göra att vi kan simulera korrelerade elektroniska material, till exempel supraledare som fungerar vid höga temperaturer. Listan över tillämpningar i det här området är mycket omfattande.

Syftet med den här dokumentationen är att tillhandahålla en kortfattad introduktion till simulering av problem med elektronisk struktur i kvantdatorer i syfte att hjälpa läsaren att förstå den roll som många aspekter av biblioteket för simulering av hamiltonska värden spelar i det området.  Vi börjar med en kort introduktion till kvantmekanik och fortsätter sedan med en diskussion av hur elektroniska system modelleras i detta område.  Sedan går vi igenom hur kvantdynamik kan emuleras med hjälp av en kvantdator.  När detta är klart diskuterar vi två metoder som används för att sammanställa kvantdynamiken till sekvenser med elementära kretsar: Trotter-Suzuki-dekompositioner och qubitisering.
