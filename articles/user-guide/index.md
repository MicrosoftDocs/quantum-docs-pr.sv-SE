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
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231765"
---
# <a name="the-no-locq-user-guide"></a>Användarhandboken för Q#

Välkommen till användarhandboken för Q#! 

I de olika avsnitten i den här vägledning introducerar vi några av grunderna för att utveckla kvantumprogram med hjälp av Q#.

Vi refererar till [vägledningen om Q#-språket](xref:microsoft.quantum.qsharp.index) för en fullständig specifikation och dokumentation av Q#-kvantprogrammeringsspråket. 

## <a name="user-guide-contents"></a>Innehåll i användarhandboken

- [Q# program](xref:microsoft.quantum.guide.programs): En snabb introduktion till kvantumprogram i Q#. 

- [Sätt att köra ett Q#-program](xref:microsoft.quantum.guide.host-programs): beskriver hur ett Q#-program körs och ger en översikt av olika sätt att anropa programmet: från kommandoraden, i Q#-Jupyter Notebooks eller från ett klassiskt värdprogram som skrivits i Python eller ett .NET-språk.

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
