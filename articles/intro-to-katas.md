---
title: Introduktion till Quantum Katas
description: Lär dig mer om de Katas (övningar) som medföljer Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 7fb8dba2a10f9a983ebee52e394260bbdc0d2f9c
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444148"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Lära sig kvantberäkning med Quantum Katas

[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) är en serie med öppen källkod som innehåller självstudier i egen takt. Du lär dig både de olika delarna inom kvantberäkning och Q#-programmering på samma gång.

## <a name="learning-by-doing"></a>Lära genom att göra

Självstudierna och de Katas som samlas in i projektet skapar inlärning med hjälp av praktiska uppgifter. De innehåller programmeringsuppgifter för vissa ämnen, från att vara mycket enkla till att vara ganska utmanande. I varje uppgift ska du fylla i viss kod. I den första uppgiften kanske enbart en rad krävs och i den sista måste du kanske ange ett stort kodfragment.

Det viktigaste är att Katas innehåller testramverk som konfigurerar, kör och validerar lösningarna på uppgifterna. På så sätt kan du få omedelbar feedback på lösningen och du kan fundera över vilken metod du ska använda om den var fel.

Du kan använda Katas till inlärning i valfri miljö:

* Jupyter Notebook online i Binder-miljö
* Jupyter Notebook som körs på den lokala datorn
* Visual Studio
* Visual Studio-koden

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Vad kan jag lära mig med Quantum Katas?

Här är en sammanfattning av de huvudsakliga ämnen som ingår i Quantum Katas. Vi rekommenderar att du följer den här utbildningsvägen i början för att se till att du har god kunskap om de grundläggande begreppen i kvantberäkning. Du kan naturligtvis hoppa över de avsnitt som du redan kan, till exempel komplex aritmetik, och du kan lära dig algoritmerna i valfri ordning.

### <a name="introduction-to-quantum-computing-concepts"></a>Introduktion till kvantberäkningsbegrepp

* [Komplex aritmetik](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic)
* [Linjär algebra](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [Kvantbitsbegreppet](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [Kvantgrindar med en kvantbit](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a>Grunderna i kvantberäkning

* [Känna igen kvantgrindar](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [Skapa en kvantsuperposition](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [Särskilja kvanttillstånd med hjälp av mätningar](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [Kopplade mätningar](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>Algoritmer

* [Kvantteleportering](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [Superdense-kodning](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [Deutsch-Jozsa-algoritm](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [Implementera Grovers sökalgoritm](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [Utforska egenskaper på hög nivå för Grovers sökalgoritm](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* Lösa verkliga problem med Grovers algoritm: [SAT-problem](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover) och [problem med diagramfärger](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)

### <a name="protocols-and-libraries"></a>Protokoll och bibliotek

* [BB84-protokoll för distribution av kvantnycklar](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* Korrigering av kvantfel: [bit-flip-fel vid korrigering av kod](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [Fasuppskattning](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* Kvantaritmetik: [skapa Ripple-Carry-adderare](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>Sammanflätningsspel

* [CHSH-spel](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [GHZ-spel](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [Mermin-Peres magiska kvadratspel](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>Resurser

* Se hela serien med [Quantum Katas](https://github.com/microsoft/QuantumKatas)
* [Köra Katas online](https://aka.ms/try-quantum-katas)