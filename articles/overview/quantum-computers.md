---
title: Vad kan kvantdatorer göra?
description: Lär dig mer om effekten av kvantberäkning, från nya kvantalgoritmer till kvantinspirerade algoritmer som körs på klassiska datorer.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: d4be970c635ca090e8dcb1b58d5c840eebd4d110
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443842"
---
# <a name="what-can-a-quantum-computer-do"></a>Vad kan en kvantdator göra?

Vad kan vi göra med en kvantdator som inte går att göra med en klassisk dator?

Om vi skulle söka efter en lösning på några av världens mest utmanande problem skulle det ta våra nuvarande datorer flera miljarder år, men en kvantdator kan göra detta på några dagar, timmar eller till och med minuter. Med kvantberäkning kan forskare utveckla nya katalysatorer och material, förbättra mediciner, påskynda framstegen inom artificiell intelligens och svara på grundläggande frågor om hur vårt universum uppstod.

## <a name="quantum-simulation"></a>Kvantsimulering

Att använda kvantprogram till att modellera själva kvantsystemen har stor möjlighet att skapa insikter som leder till innovationer i många branscher. Fotosyntes, superledare och komplexa molekyler är exempel på kvantsystem som kan simuleras med kvantprogram.

Att simulera mikroskopiska system som uppträder enligt lagarna för kvantmekanik är beräkningsmässigt mycket kostsamt. Vi måste ta hänsyn till alla möjliga tillstånd som kan finnas i en superposition och antalet tillstånd ökar exponentiellt med systemets storlek. I en kvantdator behöver vi inte modellera alla tillstånd i systemet. I stället bäddar vi in det kvanttillstånd för systemet som vi vill simulera i kvantbitarna i själva datorn och kör simuleringen med en specifik uppsättning av kvantgrindar. Med andra ord använder vi en kvantdator för att simulera ett kvantsystem.

Kemiska molekyler är kvantsystem och de kan därför analyseras på det här sättet. En sådan specifik kemikalie är enzymet _nitrogenas_ som skulle kunna minska energiförbrukningen och utsläppen av växthusgaser från gödningsmedel, om vi bara förstod dess egenskaper bättre.

## <a name="cryptography"></a>Kryptografi

Kanske finns det mest berömda programmet för kvantdatorer inom kryptografi, där Peter Shor 1994 visade att en skalbar kvantdator kan ta sig igenom all krypteringsteknik som finns.  Klassisk kryptografi förlitar sig på svårigheterna att genomföra åtgärder på stora tal, till exempel att faktorisera stora tal till två primtal.  Med kvantberäkning blir dessa åtgärder teoretiskt sett genomförbara (med hjälp av Shors algoritm). Även om en implementering av algoritmen inte är fysiskt möjlig med det nuvarande utbudet av kvantmaskinvara, har den bidragit till en utveckling av kvantresistanta algoritmer för framtidssäker datasäkerhet, inklusive nya kvantalgoritmer för kryptering och distribution av kryptografiska nycklar.  Här på Microsoft utvecklar världens ledande grupp inom postkvantkryptografi och säkerhet kvantresistenta algoritmer. 

## <a name="optimization"></a>Optimering

Optimering innebär uppgiften att utföra en stor sökning i ett mångdimensionellt utrymme för att få en verkligt bra lösning som minimerar en specifik kostnadsfunktion.   På en kvantdator kan vi påskynda optimeringen av algoritmer, vilket gör det möjligt att hitta lösningar som annars inte var genomförbara. Det finns program inom bland annat transport och logistik, sjukvård, diagnostik och materialvetenskap. Man kan tänka sig en djupgående inverkan på hur dessa branscher kan bli mer effektiva. 

När vi använder optimering med kvantberäkning kan vi förnya transporter och logistik på ett sätt som inte är möjligt med dagens klassiska system. En optimering av trafikflödet kan minska trafikstockningarna.  Förutom att planera färdsträckan, kan man ha funktioner för flygresor, paketleveranser, schemaläggning av jobb med mera.  Tack vare genombrott inom materialvetenskapen kommer det att finnas nya energikällor, batterier med större kapacitet, lättare och starkare material etc. 

## <a name="machine-learning"></a>Maskininlärning

Ett stort antal numeriska beräkningar inom klassisk databehandling består huvudsakligen i att lösa linjära system i ekvationer. Detta gäller särskilt inom maskininlärning där merparten av beräkningskostnaden går till att beräkna inversionen från enorma matriser.

Lyckligtvis finns det en kvantalgoritm som gör det möjligt för oss att på ett ungefärligt sätt lösa systemet exponentiellt snabbare än med en klassisk dator. Detta öppnar dörren till en fantastisk hastighetsökning i alla problem som behöver en lösning av linjära system i ekvationer.

Lösningar på problem inom dessa områden kan hantera energikrisen, klimatförändringar, livsmedelsbrist, samt personliga och exakta medicinska diagnoser.

## <a name="quantum-inspired-computing"></a>Kvantinspirerad beräkning

Kvantinspirerade algoritmer implementeras med klassisk programvara, men använder kvantprinciper för ökad hastighet och exakthet.

Kvantinspirerade algoritmer används vid medicinsk forskning. De kan exempelvis förbättra noggrannheten vid MR-undersökningar (magnetisk resonanstomografi). Kvantinspirerad beräkning används till att optimera konfigurationen av MR-apparaterna när vissa sjukdomar ska upptäckas.

## <a name="next-steps"></a>Nästa steg

* [Varför ska jag lära mig kvantberäkning?](xref:microsoft.quantum.overview.why)
* [Kom igång med Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
