---
title: Kvantdatorer och kvantsimulatorer
description: Lär dig mer om kvantmaskinvara, kvantsimulatorer och hur kvantåtgärder fungerar.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8691838b2d6c54baa40042245eee8c901a7ca965
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835017"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Kvantdatorer och kvantsimulatorer

Kvantdatorer är fortfarande i början av utvecklingsstadiet. Maskinvara och underhåll är dyrt, och de flesta system finns på universitet och i forskningslabb. Tekniken går dock framåt, och det finns begränsad offentlig tillgång till vissa system.

Kvantsimulatorer är program som körs på klassiska datorer och gör det möjligt att köra och testa kvantprogram i en miljö som förutsäger hur kvantbitar reagerar på olika åtgärder.

## <a name="quantum-hardware"></a>Kvantmaskinvara

Kvantdatorer omfattar tre primära delar: ett utrymme som lagrar kvantbitarna, en metod för överföring av signaler till kvantbitarna samt en klassisk dator som kör ett program och skickar instruktioner.

- Det kvantmaterial som används för kvantbitar är sårbart och mycket känsligt för miljöstörningar. För vissa metoder för kvantbitslagring hålls den enhet som lagrar kvantbitar vid en temperatur strax ovanför absolut noll så att deras koherens maximeras. Andra typer av kvantbitslagring använder en vakuumkammare för att minimera vibrationer och stabilisera kvantbitarna.  
- Signaler kan skickas till kvantbitar med en mängd olika metoder, till exempel mikrovågor, laser och spänning.

Det finns ett flertal utmaningar när det gäller korrekt drift av kvantdatorer. Felkorrigering i kvantdatorer är ett betydande problem, och uppskalning (tillägg av fler kvantbitar) ökar felfrekvensen. På grund av de här begränsningarna kommer det ta lång tid innan kvantdatorer blir tillgängliga för hemmet, men kommersiellt gångbara kvantdatorer för labb är närmare inom räckhåll.

## <a name="quantum-simulators"></a>Kvantsimulatorer

Med kvantsimulatorer som körs på klassiska datorer kan du simulera beräkning av kvantalgoritmer på ett kvantsystem.  Microsofts Quantum Development Kit (QDK) innehåller en vektorsimulator med fullständigt tillstånd samt andra specialiserade vektorsimulatorer.

## <a name="topological-qubit"></a>Topologisk kvantbit

Microsoft utvecklar en kvantdator som baseras på topologiska kvantbitar. Topologiska kvantbitar påverkas mindre av förändringar i deras miljö, vilket minskar den mängd extern felkorrigering som krävs.

Funktionen i topologiska kvantbitar ger ökad stabilitet och motståndskraft mot miljöstörningar, vilket innebär att de är enklare att skala och kan vara tillförlitliga längre.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Microsoft och partnerskap för kvantmaskinvara

Microsoft samarbetar med kvantmaskinvarutillverkarna IonQ, Honeywell och QCI för att göra kvantdatorer tillgängliga för utvecklare i framtiden. Med hjälp av Azure Quantum-plattformen kommer utvecklare att kunna använda Microsofts Quantum Development Kit (QDK) och Q# för att skriva kvantprogram och köra dem på distans.

## <a name="quantum-computations"></a>Kvantberäkningar

Utförandet av beräkningar på en kvantdator eller kvantsimulator följer en grundläggande process:

- Kom åt kvantbitarna
- Initiera kvantbitarna till önskat tillstånd
- Utför åtgärder för att transformera kvantbitarnas tillstånd
- Mät de kvantbitarnas nya tillstånd

Initiering och transformering av kvantbitar utförs med **kvantåtgärder** (som ibland kallas kvantgrindar). Kvantåtgärder liknar logikåtgärder inom klassisk beräkning, till exempel AND, OR, NOT och XOR. En åtgärd kan vara så enkel som att vända tillståndet för en kvantbit från 1 till 0 eller att sammanfläta ett par kvantbitar till att använda flera åtgärder i en sekvens för att påverka sannolikheten för att en kvantbit i superposition kollapsar åt ena eller andra hållet.

> [!NOTE] 
> [Q#-biblioteken](xref:microsoft.quantum.libraries) innehåller inbyggda åtgärder som definierar komplexa kombinationer av kvantåtgärder på lägre nivå. Du kan använda biblioteksåtgärderna för att transformera kvantbitar och skapa mer komplexa användardefinierade åtgärder.  

Mätning beräkningsresultatet ger oss ett svar, men för vissa kvantalgoritmer är svaret inte nödvändigt rätt. Eftersom resultatet av vissa kvantalgoritmer baseras på den sannolikhet som konfigurerades av kvantåtgärderna körs dessa beräkningar flera gånger för att skapa en sannolikhetsdistribution och öka resultatets noggrannhet.  Försäkran om att en åtgärd returnerade rätt svar kallas kvantverifiering. Detta är en betydande utmaning inom kvantberäkning.

## <a name="summary"></a>Sammanfattning

Kvantberäkning delar vissa begrepp med klassisk beräkning men har även vissa särdrag. Här är en sammanfattning av några viktiga punkter:

- Kvantmaskinvara är dyr och ömtålig att arbeta med, och därför används kvantsimulatorer för skrivande och testning av program.
- Både klassiska datorer och kvantdatorer använder logikåtgärder (eller grindar) för att förbereda beräkningar.
- Kvantberäkningar returnerar sannolikheter.

Framsteg inom kvantmaskinvara och kvanttekniker leder till snabb förändring av branschen. Här är några exempel inom den [aktuella utvecklingen](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Nästa steg

[Vad är programmeringsspråket Q# och QDK?](xref:microsoft.quantum.overview.q-sharp)
