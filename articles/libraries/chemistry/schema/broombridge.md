---
title: Broombridge – Quantum kemi-schema
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: c2a7636d0b3f07419e3312e04da5d811229ad854
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185332"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge Quantum kemi-schema # 

Kraftfull kemi-programvara som [NWChem](http://www.nwchem-sw.org/) gör det möjligt att modellera ett brett utbud av kemi-problem i Real världen. För att få åtkomst till NWChem molekyl modeller med Microsoft Quantum kemi-biblioteket använder vi ett [yaml](https://en.wikipedia.org/wiki/YAML)schema som vi kallar **Broombridge**. Namnet valdes i referens till ett [landmärke](https://en.wikipedia.org/wiki/Broom_Bridge) som i vissa cirklar är celebrated som en Birthplace för Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) är ett projekt med öppen källkod som licensieras enligt ECL () 2,0 licens. Broombridge är ett schema med öppen källkod som anges [här](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) och som levereras med en [definition](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) som följer [RFC 2119](https://tools.ietf.org/html/rfc2119) och [verifierings skriptet](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licensierat under MIT-licensen. 

Broombridge är ett strukturerat, mänskligt och läsligt sätt att representera problem med den elektroniska strukturen. I synnerhet kan följande data visas: 
- Fermionic Hamiltonians kan representeras med hjälp av en-och två-Electron integraler. 
- Mark-och spännande tillstånd kan visas med hjälp av sekvenser.
- De övre och nedre gränserna för energi nivåer kan anges.

Data formatet kan genereras från NWChem på ett enkelt sätt: en mängd olika metoder är tillgängliga som sträcker sig från en fullständig installation av NWChem för att köra kemi-däck som de som anges [här](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) och utdata Broombridge som en del av körningen, över en Docker bild av NWchem som också kan användas för att generera Broombridge från kemi-däck. Slutligen är en visuell metod för att komma igång med beräknings kemi snabbt utan att behöva installera någon kemi-programvara från [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) -gränssnittet till NWChem. 

På hög nivå kan samspelet mellan NWChem och Microsoft Quantum Development Kit visualiseras på följande sätt: ![kemi stack](~/media/broombridge.png) den blå skuggade rutan representerar Broombridge-schemat, de olika grå skuggade rutorna representerar andra interna data representationer som valts för att representera och bearbeta Quantum-algoritmer för beräkning av kemi baserat på kemi problem i Real världen. 

Det finns flera kemiska representationer som definieras med Broombridge-schemat [här](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).

