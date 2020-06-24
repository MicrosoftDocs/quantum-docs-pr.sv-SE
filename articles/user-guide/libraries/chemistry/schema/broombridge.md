---
title: Broombridge Quantum kemi-schema
description: Översikt över Broombridge Quantum kemi-schemat som används för att utforma verkliga kemi-problem med Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275878"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge Quantum kemi-schema # 

Kraftfull kemi-programvara som [NWChem](http://www.nwchem-sw.org/) gör att du kan modellera ett brett utbud av kemi-problem i Real världen. För att få åtkomst till NWChem molekyl modeller med Microsoft Quantum kemi-biblioteket använder du ett [yaml](https://en.wikipedia.org/wiki/YAML)-baserat schema med namnet **Broombridge**. Namnet valdes i referens till ett [landmärke](https://en.wikipedia.org/wiki/Broom_Bridge) som i vissa cirklar är celebrated som en Birthplace för Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) är ett projekt med öppen källkod som licensieras enligt ECL () 2,0 licens. [Broombridge Quantum kemi-schemat](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) är ett schema med öppen källkod som innehåller en [definition](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) som följer [RFC 2119](https://tools.ietf.org/html/rfc2119) och ett [VERIFIERINGs skript](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) som licensieras enligt MIT-licensen. 

Broombridge är ett strukturerat, mänskligt och läsligt sätt att representera problem med den elektroniska strukturen. I synnerhet kan följande data visas:
- Fermionic Hamiltonians kan representeras med hjälp av en-och två-Electron integraler.
- Mark-och spännande tillstånd kan visas med hjälp av sekvenser.
- De övre och nedre gränserna för energi nivåer kan anges.

Data kan genereras från NWChem med olika metoder, till exempel att använda en fullständig installation av NWChem för att köra kemi-däck (till exempel de som finns i [NWChem-biblioteket](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) som utvärderar Broombridge som en del av körningen) eller en Docker-avbildning av NWChem som också kan användas för att generera Broombridge från kemi-däck. För att komma igång med beräknings kemi snabbt utan att behöva installera någon kemi-programvara, kan du använda det visuella gränssnittet till NWChem som tillhandahålls av [EMSL-pilarna](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

På en hög nivå kan samspelet mellan NWChem och Microsoft Quantum Development Kit visualiseras på följande sätt: ![ kemi stack ](~/media/broombridge.png) den blå skuggade rutan representerar Broombridge-schemat, de olika grå skuggade rutorna representerar andra interna data representationer som valts för att representera och bearbeta Quantum-algoritmer för beräkning av kemi-problem i Real världen.

Mappen [integral/yaml](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) i exempel databasen i Quantum Development Kit innehåller flera kemiska representationer som definieras med Broombridge-schemat.
