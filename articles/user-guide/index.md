---
title: Användarhandboken för Q#
description: Översikt över användarhandbokens syfte och innehåll
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771384"
---
# <a name="the-no-locq-user-guide"></a>Användarhandboken för Q#

Välkommen till användarhandboken för Q#! 

I de olika ämnena i den här guiden går vi igenom huvudbegreppen i språket Q#. Du får all information som du behöver för att skriva kvantprogram.

## <a name="user-guide-contents"></a>Innehåll i användarhandboken

- [Grunderna om Q#](xref:microsoft.quantum.guide.basics): En introduktionsöversikt om syftet med och funktionerna i programmeringsspråket Q#. 

- [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs): beskriver hur ett Q#-program körs och ger en översikt av olika sätt att anropa programmet: från kommandoraden, i Q#-Jupyter Notebooks eller från ett klassiskt värdprogram som skrivits i Python eller ett .NET-språk.

### <a name="no-locq-language"></a>Språket Q#

- [Typer i Q#](xref:microsoft.quantum.guide.types): Beskriver typmodellen i Q# och den syntax som används för att ange och arbeta med typer.

- [Typuttryck](xref:microsoft.quantum.guide.expressions): Beskriver hur du anger, refererar till, kombinerar och arbetar med värden för varje typ i Q#. 

### <a name="using-no-locq"></a>Använda Q#

- [Filstruktur för Q#](xref:microsoft.quantum.guide.filestructure): Beskriver strukturen och syntaxen för en `*.qs` Q#-fil.

- [Åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions): Beskriver de två anropningsbara typerna i språket Q#: *åtgärder*, som används för åtgärder med kvantbitsregister, samt *funktioner*, som enbart används med klassisk information. 
    Här kan du se hur du definierar och anropar dem, inklusive relaterade och kontrollerade versioner av kvantåtgärder.

- [Variabler](xref:microsoft.quantum.guide.variables): Beskriver variablernas roll i Q#-program och hur du använder dem på ett effektivt sätt. 
    Du hittar till exempel information om bindande omfång och om skillnaden mellan oföränderliga och föränderliga variabler och hur du tilldelar eller omtilldelar dem.

- [Arbeta med kvantbitar](xref:microsoft.quantum.guide.qubits): Beskriver de funktioner i Q# som används för enskilda kvantbitar och system med kvantbitar, mer specifikt hur du allokerar dem, utför åtgärder på dem och mäter dem. 

- [Kontrollflöde](xref:microsoft.quantum.guide.controlflow): Beskriver kontrollflödesmönstren för programmering i Q# som har stöd för många standardtekniker (till exempel villkorsstyrd bearbetning, *for*-loopar och *while*-loopar) samt det kvantspecifika *upprepa-tills-lyckas*-mönstret.

- [Testa och felsöka](xref:microsoft.quantum.guide.testingdebugging): Beskriver några tekniker som du kan använda för att se till att koden gör det den ska göra. 
    På grund av den övergripande komplexiteten i kvantinformation, kan det krävas särskilda tekniker när kvantprogram ska felsökas. 
    Lyckligtvis stöder Q# många av de klassiska felsökningstekniker som programmerare är vana vid samt även dem som är kvantspecifika. Dessa omfattar tekniker som att skapa och köra enhetstester i Q#, att bädda in *kontroller* för värden och sannolikheter i koden samt `Dump`-funktioner som visar måldatorernas tillstånd. 
    Den senare kan användas tillsammans med vår simulator med fullständigt tillstånd för att felsöka särskilda delar av beräkningarna genom att kringgå vissa kvantbegränsningar, t.ex. [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).

### <a name="quantum-simulators-and-resource-estimators"></a>Kvantsimulatorer och resursberäknare

- [Kvantsimulatorer och värdprogram](xref:microsoft.quantum.machines): En översikt av de olika tillgängliga simulatorerna samt hur värdprogram och måldatorer fungerar ihop för körning av Q#-program.

- [Simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator): Måldatorn som simulerar det fullständiga kvanttillståndet. Användbart för fullständig körning eller felsökning av program i mindre skala (mindre än ett dussintal kvantbitar)

- [Resursberäknare](xref:microsoft.quantum.machines.resources-estimator): Beräknar de resurser som krävs för att köra en specifik instans av en Q#-åtgärd på en kvantdator.

- [Spårningssimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator. Det kan därför köra kvantprogram som använder tusentals kvantbitar. Användbart för felsökning av klassisk kod i ett kvantprogram, samt för att beräkna de resurser som krävs.

- [Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator): En specialutvecklad kvantsimulator som kan användas med flera miljoner kvantbitar, men endast för program med en begränsad uppsättning kvantåtgärder – X, CNOT och multistyrd X.

### <a name="quick-reference-pages"></a>Snabbreferenssidor

- [Magiska IQ#-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp): Snabbreferenssida för magiska IQ#-kommandon i Q#-Jupyter Notebooks.
