---
title: Användarhandboken för Q#
description: Översikt över användarhandbokens syfte och innehåll
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430619"
---
# <a name="the-q-user-guide"></a>Användarhandboken för Q#

Välkommen till användarhandboken för Q#! 

Här går vi igenom huvudbegreppen i språket Q#, och du får all information som du behöver för att skriva kvantprogram.

## <a name="user-guide-contents"></a>Innehåll i användarhandboken

- [Grunderna i Q#](xref:microsoft.quantum.guide.basics): En introduktionsöversikt om syftet med och funktionerna i programmeringsspråket Q#. 

### <a name="q-language"></a>Språket Q#

- [Typer i Q#](xref:microsoft.quantum.guide.types): Beskriver typmodellen i Q# och syntaxen som används för att ange och arbeta med typer.

- [Typuttryck](xref:microsoft.quantum.guide.expressions): Beskriver hur du anger, refererar till, kombinerar och arbetar med värden för varje typ i Q#. 

### <a name="using-q"></a>Använda Q#

- [Q#-filstruktur](xref:microsoft.quantum.guide.filestructure): Beskriver strukturen och syntaxen för en `*.qs`-Q#-fil.

- [Åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions): Beskriver de två anropningsbara typerna i Q#-språket: *åtgärder*, som används för åtgärder med kvantbitsregister, samt *funktioner*, som enbart används med klassisk information. 
    Här kan du se hur du definierar och anropar dem, inklusive relaterade och kontrollerade versioner av kvantåtgärder.

- [Variabler](xref:microsoft.quantum.guide.variables): Beskriver variablernas roll i Q#-program och hur du använder dem på ett effektivt sätt. 
    Du hittar till exempel information om bindande omfång och om skillnaden mellan oföränderliga/föränderliga variabler och hur du tilldelar/omtilldelar dem.

- [Arbeta med kvantbitar](xref:microsoft.quantum.guide.qubits): Beskriver de funktioner i Q# som används för enskilda kvantbitar och system med kvantbitar. 
    Det innebär mer specifikt deras allokering, att utföra åtgärder på dem och slutligen deras mått. 

- [Kontrollflöde](xref:microsoft.quantum.guide.controlflow): Beskriver kontrollflödesmönstren för programmering i Q#, som har stöd för många standardtekniker (villkorlig körning, for-loopar, while-loopar osv.) samt det kvantspecifika ”upprepa-tills-lyckas”-mönstret.

- [Testa och felsöka](xref:microsoft.quantum.guide.testingdebugging): Beskriver några tekniker som du kan använda för att se till att koden gör det den ska göra. 
    På grund av den övergripande komplexiteten i kvantinformation, kan det krävas särskilda tekniker när kvantprogram ska felsökas. 
    Lyckligtvis stöder Q# många av de klassiska felsökningstekniker som programmerare brukar använda, samt även de som är kvantspecifika. Detta innefattar att skapa/köra enhetstester i Q#, bädda in *kontroller* av värden och sannolikheter i koden, samt `Dump`-funktioner som visar status för måldatorn. 
    Den senare kan användas tillsammans med vår simulator med fullständigt tillstånd för att felsöka särskilda delar av beräkningarna genom att kringgå vissa kvantbegränsningar (t.ex. ”no-cloning theorem”).

### <a name="quantum-simulators-and-resource-estimators"></a>Kvantsimulatorer och resursberäknare

- [Kvantsimulatorer och värdprogram](xref:microsoft.quantum.machines): En översikt över de olika tillgängliga simulatorerna, samt den generella modellen för körning mellan värdprogram och måldatorer.

- [Simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator): Måldatorn som simulerar det fullständiga kvanttillståndet. Användbart för fullständig körning eller felsökning av program i mindre skala (mindre än ett par dussin kvantbitar)

- [Resursberäknare](xref:microsoft.quantum.machines.resources-estimator): Beräknar de resurser som krävs för att köra en specifik instans av en Q#-åtgärd på en kvantdator.

- [Spårningssimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator och kan därför köra kvantprogram som använder tusentals kvantbitar. Användbart för felsökning av klassisk kod i ett kvantprogram, samt för att beräkna de resurser som krävs.

- [Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator): En specialutvecklad kvantsimulator som kan användas med flera miljoner kvantbitar, men endast för program med en begränsad uppsättning kvantåtgärder (närmare bestämt X, CNOT och multistyrd X).

### <a name="quick-reference-pages"></a>Snabbreferenssidor

- [Magiska kommandon för IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Snabbreferenssida för magiska kommandon för IQ# i Q# Jupyter Notebooks.
