---
title: Program varu stack | Microsoft Docs
description: Program varu stack
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184737"
---
# <a name="software-stack-for-quantum-computing"></a>Program varu stack för Quantum Computing
Normalt när vi tänker på en dator vi Envision en enda enhet som kör ett program, men moderna dator miljöer är mycket mer komplexa och avancerade. Det program vi interagerar med brukar finnas på flera lager program som tillhandahåller program körningen på maskin varu nivå. De här program varu lagren är nödvändiga för att kunna sammanfatta utvecklingen av en program lösning från den underliggande komplexiteten hos hela data behandlings systemet. Om en utvecklare måste tänka på buss, cache-arkitekturer, kommunikations protokoll och mer när du skriver en enkel smartphone-app skulle uppgiften bli mycket mer komplex.  Begreppet *program varu stack* har utvecklats i klassiskt data behandling för att åtgärda problemen.  Om du lånar från det klassiska konceptet är en program varu stack också en viktig del av insikten bakom Quantum Computing med Q #.

## <a name="conventional-stack"></a>Konventionell stack
Den viktiga idén bakom en program varu stack är rekursion.  Det består av flera kapslade lager med gränssnitt som sammanfattar information om de lägre nivåerna av enheten bort från utvecklaren.  En vanlig program varu stack inbegriper till exempel att köra ASP.NET (ett programmeringsspråk), ovanpå SQL Server (ett Relations databas hanterings system), som körs ovanpå Internet Information Services (en webb server) som körs ovanpå Windows Server (en operativ system), som driver dator maskin varan.  Genom att titta på program vara som en hierarki kan du skriva program vara i ASP.NET utan att behöva förstå information på låg nivå för all program vara under den.

## <a name="quantum-stack"></a>Quantum-stack

Program varu stacken i Quantum Computing är inte annorlunda i princip, och i praktiken fungerar en lägre nivå än traditionella stackar.  Vad ser en Quantum-stack ut?  En Quantum-dator ersätter inte traditionella (ofta kallade klassiska) datorer.  Quantum-datorer kommer i själva verket att arbeta tillsammans med klassiska datorer för att lösa beräknings problem.  Detta beror delvis på fragility av Quantum-data.  Quantum data är så känsliga att om du tittar på det nästan verkligen skadar du informationen som observeras.  Quantum-datorer måste därför utformas med Quantum-fel korrigering i åtanke så att lösa interaktioner från dess fysiska miljö inte oavsiktligt skadar informationen och beräkningen. Av den anledningen är ett naturligt mål för Q # en felkorrigerad Quantum-dator (kallas ofta en *feltolerant* Quantum-dator) som accepterar en lista med Quantum-instruktioner (kallas grindar eller grind åtgärder) och tillämpar anvisningarna på Quantum data som lagras i den.  Observera att om antalet qubits-och grind åtgärder i en Quantum-algoritm eller ett program är tillräckligt litet, kanske fel korrigeringen inte är absolut nödvändig.  Men eftersom antalet qubits-och grind åtgärder växer är det mer effektivt att ha ett krav, vilket innebär att vi skapar vår program varu stack och Q # till aptly och effektivt hanterar fel korrigering och möjliggör skalbar, feltolerant Quantum-bearbetning.

### <a name="error-correction"></a>Fel korrigering
Vid fel korrigering krävs en snabb och tillförlitlig klassisk dator som kan köras tillsammans med Quantum-datorn för att korrigera fel när de visas i Quantum-beräkningen.  I praktiken kan komponenter som till exempel FPGAs (Field-programmerbara grind mat ris) eller snabba cryogenic-processorer behövas för att identifiera och korrigera felen snabbare än de naturligt ackumulerade i Quantum-datorn.  Därför är en Quantum-dator en hybrid dator som består av flera olika beräknings enheter som fungerar över en mängd olika temperaturer.  Därför är det mycket mer användbart att tänka på att programmering av en Quantum-dator genom en program varu Stacks lins, eftersom det finns många lager av maskin vara och program vara (klassisk och Quantum) som krävs för att slutligen uppnå implementeringen av en Quantum algoritm på en Quantum-dator.

### <a name="quantum-conceptual-stack"></a>Quantum konceptuell stack
En konceptuell stack som illustrerar det funktionella flödet av factoring 8704143553785700723 i en Quantum computing-miljö visas nedan:

![Program varu stack](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Specifikation och algoritm
Det finns flera olika stadier i programmering, till exempel en Quantum-beräkning.  Den första och utan tvekan mest utmanande fasen är att ange det problem som en vill lösa.  I det här fallet är problemet att Factor the Number 8704143553785700723 i en produkt med två primtal.  Nästa steg innebär att utforma en algoritm för att lösa det här beräknings problemet.  I det här fallet kan Shor berömda Quantum factoring-algoritmen användas för att hitta faktorerna.  Den här algoritmen uttrycks i Q # och sedan är en sekvens med Quantum-åtgärder utdata som kan köras på en idealisk dator utan problem.  

### <a name="physical-gates"></a>Fysiska portar
I det här exemplet är det inte så av typen att tillhandahålla en felfri Quantum-dator, så efterföljande steg tar de åtgärder som släpps av Q # och översätter dem med hjälp av mallar som anges av den Quantum-fel korrigerings metod som valts i fysiska grindar som den grundläggande maskin varan kan köras.  Den här processen omfattar att ersätta varje logisk qubit som beskrivs i den tidigare modellen med en värd med fysiska qubits som används för att lagra och skydda informationen i en enskild qubit i en redundant miljö som kan motstå lokala fel på den fysiska komponenten qubits tillräckligt länge för att sådana fel ska kunna identifieras och korrigeras.  Precis som de logiska qubits som beskrivs av Q #-koden måste ersättas med många fysiska qubits, så måste varje Quantum-grind som beskrivs i utdata översättas till en sekvens med fysiska portar som fungerar på den fysiska qubits.  Därför är utmatningen av Q # sällan det slutliga målet för Quantum Computing och ytterligare nivåer av abstraktion krävs för att köra koden på maskin vara på ett Oblivious sätt.

### <a name="control-computer"></a>Kontrol lera dator
Den fysiska gaten läses sedan in i en vanlig dator som skickar instruktionerna till en kontroll dator som är gränssnitts direkt med den Quantum-datorn.  Detta skikt i program varu stacken hanteras ofta av experimentell kontroll program som [QCoDeS](http://qcodes.github.io/Qcodes/).

### <a name="interface-computer"></a>Gränssnitts dator
Det sista steget i den här processen omfattar att gränssnitts datorn först strömma portarna efter behov till en snabb kontroll dator. Sedan använder den snabba kontroll datorn de spänningar som krävs (vanligt vis kallade pulser) för att implementera de nödvändiga portarna på qubits. Detta måste göras när du korrigerar eventuella fel som observeras genom Quantum Error-korrigering.  Cryogenic FPGAs eller annan exotiska maskin vara kan behövas för att utföra dessa steg inom de stränga tids krav som anges av den hastighet med vilken fel visas på datorn Quantum.  Mål språket på den här nivån är ofta [VHDL](https://en.wikipedia.org/wiki/VHDL), vilket kräver ett tydligt sätt att fundera från det som används längst upp i stacken för att analysera en beskrivning av en Quantum-algoritm.

### <a name="the-q-quantum-programming-language"></a>Programmeringsspråket Q # Quantum
Syftet med Q # är att tillhandahålla ett enkelt språk som gör det möjligt för utvecklare att skriva kod som är riktad till en mängd olika plattformar och gränssnitt med de mellanliggande lagren av program vara som ligger mellan användaren och Quantum-enheten.  Språket fören klar detta genom att använda begreppet program varu stack och att sammanföra många detaljer i den underliggande Quantum-datorn samtidigt som du tillåter andra nivåer av stacken, som visas på ett språk som C#, för att utföra nödvändiga översättningar från Q # Code till grundläggande åtgärder.  Detta gör att utvecklaren kan fokusera på vad de gör bäst: att utforma algoritmer och lösa problem.
