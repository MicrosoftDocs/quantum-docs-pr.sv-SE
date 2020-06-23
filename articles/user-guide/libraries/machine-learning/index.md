---
title: Introduktion till Quantum Machine Learning-paketet | Microsoft Docs
description: Introduktion till Quantum Machine Learning-paketet
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274005"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introduktion till Quantum Machine Learning-biblioteket

Quantum Machine Learning-biblioteket är ett API, skrivet i Q#, som ger dig möjlighet att köra kvant-/klassiska hybridinlärningsexperiment. Med biblioteket kan du:

- Läsa in dina egna data och klassificera med kvantsimulatorer

- Använd exempel och självstudier för att bekanta dig med kvantmaskininlärning

Du kan förvänta dig låga prestanda jämfört med aktuella klassiska ramverk för maskininlärning (kom ihåg att allt körs ovanpå simuleringen av en kvantenhet som beräkningsmässigt redan är mycket dyr).

Syftet med det här dokumentet är:

- En kortfattad introduktion till maskininlärningsverktyg (skrivna i Q\#) för kvant-/klassisk maskininlärning.
- Introducera maskininlärningskoncept och särskilt deras realisering i kvantkretscentrerade klassificerare (kallas även sekventiella kvantklassificerare).
- Tillhandahålla en serie självstudier om grunderna för att börja använda verktygen som finns i biblioteket.
- Beskriva inlärnings- och valideringsmetoderna för sådana klassificerare och hur de översätts till specifika Q\#-åtgärder som tillhandahålls av biblioteket.

Modellen som implementeras i det här biblioteket baseras på det klassiska kvantinlärningsschemat som presenteras i [Kretsbaserade kvantklassificerare](https://arxiv.org/abs/1804.00633)
