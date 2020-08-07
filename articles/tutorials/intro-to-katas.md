---
title: Introduktion till Quantum Katas
description: Lär dig mer om de Katas (övningar) som medföljer Microsoft Quantum Development Kit (QDK)
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a3b25bf90109468f02c98c6c687befb83648bc
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869689"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Lära sig kvantberäkning med Quantum Katas

[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) är en öppen källkod, självstudier och programmerings övningar som syftar till att lära sig elementen i Quantum data behandling och Q# programmering på samma tidpunkt.

## <a name="learning-by-doing"></a>Lära genom att göra

Självstudierna och övningarna som samlas in i projektet skapar inlärning med hjälp av praktiska uppgifter. De innehåller programmeringsuppgifter för vissa ämnen, från att vara mycket enkla till att vara ganska utmanande. I varje uppgift ska du fylla i viss kod. I den första uppgiften kanske enbart en rad krävs och i den sista måste du kanske ange ett stort kodfragment.

Det viktigaste är att Katas innehåller test ramverk som konfigurerar, kör och validerar lösningarna för aktiviteterna. På så sätt kan du få omedelbar feedback på lösningen och du kan fundera över vilken metod du ska använda om den var fel.

Du kan använda Katas för inlärning i valfri miljö:

* Jupyter Notebook online i Binder-miljö
* Jupyter Notebook som körs på den lokala datorn
* Visual Studio
* Visual Studio-koden

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Vad kan jag lära mig med Quantum Katas?

Utforska grunderna och grunderna i Quantum Computing eller gå djupare till Quantum-algoritmer och protokoll. Vi rekommenderar att du följer den här utbildningsvägen i början för att se till att du har god kunskap om de grundläggande begreppen i kvantberäkning. Du kan naturligtvis hoppa över de avsnitt som du redan kan, till exempel komplex aritmetik, och du kan lära dig algoritmerna i valfri ordning.

### <a name="introduction-to-quantum-computing-concepts"></a>Introduktion till kvantberäkningsbegrepp

| Kata | Beskrivning |
|:-----|-------------|
|[Komplex aritmetik](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|I den här självstudien beskrivs en del av den matematiska bakgrunden som krävs för att arbeta med Quantum Computing, till exempel imaginära och komplexa tal.|
|[Linjär algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|Linjär algebra används för att representera Quantum-tillstånd och åtgärder i Quantum Computing. I den här självstudien beskrivs grunderna, inklusive matriser och vektorer.|
|[Kvantbitsbegreppet](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|Lär dig mer om qubits – en av kärn koncepten för Quantum Computing. |
|[Kvantgrindar med en kvantbit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|I den här självstudien introduceras en qubit Quantum-grind, som fungerar som bygg stenar av Quantum-algoritmer och transformera Quantum qubit-tillstånd på olika sätt.|
|[System med flera kvantbitar](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|I den här självstudien introduceras qubit system, deras representation i matematisk notation och i Q# kod samt begreppet entanglement.|
|[Qubit Quantum Gates](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Den här självstudien följer själv studie kursen om [en qubit Quantum Gates](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) och fokuserar på att tillämpa Quantum-grindar på qubit-system.|

### <a name="quantum-computing-fundamentals"></a>Grunderna i kvantberäkning

| Kata | Beskrivning |
|:-----|-------------|
|[Känna igen kvantgrindar](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|En serie övningar utformade för att bekanta dig med de grundläggande Quantum-portarna i Q# . Innehåller övningar för grundläggande qubit-och multi-qubit-portar, intilliggande och kontrollerade portar och hur man använder portar för att ändra tillstånd för en qubit.|
|[Skapa en kvantsuperposition](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Använd de här övningarna för att bekanta dig med begreppet överposition och programmering i Q# . Innehåller övningar för grundläggande qubit-och multi-qubit-portar, superposition och flödes kontroll och rekursion i Q# .|
|[Särskilja kvanttillstånd med hjälp av mätningar](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Lös de här övningarna och lär dig om Quantum-mått och rätvinkliga och icke-rätvinkliga stater. |
|[Kopplade mätningar](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Lär dig mer om gemensamma paritets mätningar och hur du använder [mått](xref:microsoft.quantum.intrinsic.measure) åtgärden för att särskilja Quantum-tillstånd.|

### <a name="algorithms"></a>Algoritmer

| Kata | Beskrivning |
|:-----|-------------|
|[Kvantteleportering](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|Den här Kata utforskar Quantum Telecommunication – ett protokoll som gör det möjligt att kommunicera ett Quantum-tillstånd med enbart klassisk kommunikation och tidigare delade Quantum entanglement.|
|[Superdense-kodning](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|Upptätad kodning är ett protokoll som tillåter överföring av två bitar av klassisk information genom att bara skicka en qubit med hjälp av den tidigare delade Quantum-entanglement.  |
|[Deutsch-Jozsa-algoritm](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Den här algoritmen är berömda för ett av de första exemplen i en Quantum-algoritm som är exponentiellt snabbare än en deterministisk klassisk algoritm.|
|[Utforska egenskaper på hög nivå för Grovers sökalgoritm](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|En hög nivå introduktion till en av de mest berömda-algoritmerna i Quantum Computing. Det löser problemet med att hitta indata till en svart ruta (Oracle) som skapar en viss utmatning. |
|[Implementera Grovers sökalgoritm](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Den här Kata-dykningar är djupare i sökalgoritmen för Grover och täcker att skriva Oracle, utföra steg i algoritmen och sedan lägga ihop allt tillsammans.|
|[Lösa verkliga problem med Grover-algoritmen: söt problem](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|En serie övningar som använder algoritmen Grover för att lösa realistiska problem, med hjälp av [booleska problem](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (söt) som exempel.  |
|[Lösa verkliga problem med Grover-algoritmen: problem med Graf färgning](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Den här Kata utforskar ytterligare Grover-algoritmen, den här gången för att lösa [problem](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem)med problem med en graf som exempel. |

### <a name="protocols-and-libraries"></a>Protokoll och bibliotek

| Kata | Beskrivning |
|:-----|-------------|
|[BB84-protokoll för distribution av kvantnycklar](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Läs om och implementera ett Quantum Key Distribution Protocol, [BB84](https://en.wikipedia.org/wiki/BB84), med hjälp av qubits till Exchange-kryptografiska nycklar. |
|[Bit-flip fel vid korrigering av kod](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|Utforska Quantum-felkorrigeringen med den enklaste av Quantum Error-Correction (QEC) Codes (qubit bit-flip kod).|
|[Fasuppskattning](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|Algoritmer för fas uppskattning är några av de mest grundläggande Bygg stenarna för Quantum Computing. Lär dig mer om fas uppskattning med de här övningarna som beskriver uppskattning av Quantum-fasen och hur du förbereder och kör fas uppskattnings rutiner i Q# .|
|[Quantum-aritmetiska: skapa krusning – bär Adders](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|En djupgående serie med övningar som utforskar [krusningar](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) som har lagts till på en Quantum-dator. Bygg en egenskapsangivning Quantum-, utöka den med en annan algoritm och bygg sedan en på plats en Quantum-under traktor.   |

### <a name="entanglement-games"></a>Sammanflätningsspel

| Kata | Beskrivning |
|:-----|-------------|
|[CHSH-spel](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|Utforska Quantum entanglement med en implementering av [CHSH](https://en.wikipedia.org/wiki/CHSH_inequality) -spelet. Detta [icke-lokala](https://en.wikipedia.org/wiki/Quantum_refereed_game) spel visar hur Quantum entanglement kan användas för att öka spelarens chans att vinna mer än vad som skulle vara möjligt med en helt klassisk strategi.|
|[GHZ-spel](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|GHZ-spelet är ett annat icke-lokalt spel, men omfattar tre spelare.|
|[Mermin-Peres magiska kvadratspel](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|En serie övningar som utforskar [Quantum pseudo-telepathy](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) för att lösa ett magiskt fyrkantigt spel.  |

## <a name="resources"></a>Resurser

Se hela serien med [Quantum Katas](https://github.com/microsoft/QuantumKatas)

[Köra Katas online](https://aka.ms/try-quantum-katas)
