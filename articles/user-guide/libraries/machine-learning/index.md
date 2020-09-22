---
title: Introduktion till Quantum Machine Learning-paketet | Microsoft Docs
description: Introduktion till Quantum Machine Learning-paketet
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 321901a7976e4633a672495827c27c5f1645ad30
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835697"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introduktion till Quantum Machine Learning-biblioteket

Quantum Machine Learning-biblioteket är ett API, skrivet i Q#, som ger dig möjlighet att köra kvantbaserade/klassiska hybridexperiment för maskininlärning. Med biblioteket kan du:

- Läsa in dina egna data och klassificera med kvantsimulatorer

- Använd exempel och självstudier för att bekanta dig med kvantmaskininlärning

Du kan förvänta dig låga prestanda jämfört med aktuella klassiska ramverk för maskininlärning (kom ihåg att allt körs ovanpå simuleringen av en kvantenhet som beräkningsmässigt redan är mycket dyr).

Syftet med det här dokumentet är:

- En kortfattad introduktion till maskininlärningsverktyg (skrivna i Q\#) för kvant-/klassisk maskininlärning.
- Introducera maskininlärningskoncept och särskilt deras realisering i kvantkretscentrerade klassificerare (kallas även sekventiella kvantklassificerare).
- Tillhandahålla en serie självstudier om grunderna för att börja använda verktygen som finns i biblioteket.
- Beskriva inlärnings- och valideringsmetoderna för sådana klassificerare och hur de översätts till specifika Q\#-åtgärder som tillhandahålls av biblioteket.

Modellen som implementeras i det här biblioteket baseras på det klassiska kvantinlärningsschemat som presenteras i [Kretsbaserade kvantklassificerare](https://arxiv.org/abs/1804.00633)
