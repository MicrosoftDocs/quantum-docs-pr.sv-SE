---
title: Kvantutvecklingstekniker | Microsoft Docs
description: Kvantutvecklingstekniker
keywords: Lägg inte till eller redigera nyckelord utan att först kontakta den SEO-ansvarige.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: c1263edb75f903702ab3c16cec0443857150b662
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820818"
---
# <a name="quantum-development-techniques"></a>Kvantutvecklingstekniker

I det här avsnittet av dokumentationen beskrivs de grundläggande begrepp som används för att skapa kvantprogram i Q#, samt hur man interagerar med dessa program från klassiska program.
Vi antar att du har *viss* kunskap om kvantberäkning, t.ex. de som beskrivs i [Begrepp inom kvantberäkning](xref:microsoft.quantum.concepts.intro), men du behöver inte vara expert på kvantberäkning för att förstå dessa avsnitt.

Innehållet är följande.

- I [Översikt över Q#-programmet](xref:microsoft.quantum.techniques.file-structure) finns en översikt över syftet med och funktionerna i programmeringsspråket Q#. 
    I synnerhet klargörs hur Q# *inte* ett språk som enbart simulerar kvantmekanik – även om den funktionen givetvis finns i vår simulator med fullständigt tillstånd. 
    I stället har Q# utformats med tanke på framtiden och i programmen beskrivs hur en klassisk kontrolldator *interagerar* med kvantbitar. 

- I [Åtgärder och funktioner](xref:microsoft.quantum.techniques.opsandfunctions) visas de två anropningsbara typerna av Q#-språket: *Åtgärder* som innehåller åtgärder för kvantbitar och kvantsystem, samt *funktioner* som enbart arbetar med klassisk information. 
    Om inte både klassisk information och kvantinformation kunde användas samtidigt, skulle kvantberäkningen vara omöjlig. 
    I det här avsnittet beskrivs hur du definierar och använder dessa anropningsbara typer i kontrollflödet för ett Q#-program.

- I [Lokala variabler](xref:microsoft.quantum.techniques.local-variables) beskrivs variablernas roll i Q#-program och hur du använder dem på ett effektivt sätt. 
    I synnerhet kommer du att lära dig skillnaden mellan oföränderliga/föränderliga variabler och hur du tilldelar/omtilldelar dem.

- I [Arbeta med kvantbitar](xref:microsoft.quantum.techniques.qubits) beskrivs de funktioner i Q# som du kan använda för enskilda kvantbitar och system med kvantbitar. 
    Det innebär mer specifikt deras allokering, att utföra åtgärder på dem och slutligen deras mått. 
    Dessutom får du lära dig några användbara kontrollflödestekniker.

- I [Färdigställa allt](xref:microsoft.quantum.techniques.puttingittogether) använder du teknikerna från avsnitten ovan till att skapa ett program som utför **kvantteleportering**: Med hjälp av två klassiska bitar ”teleporteras” hela tillståndet i en kvantbit till en annan.

- I [Gå vidare](xref:microsoft.quantum.techniques.going-further) introduceras avancerade tekniker som kan vara till hjälp när du går vidare mot mer komplex kvantprogrammering. 
    I synnerhet diskuterar vi användningen av *typparametriserade* åtgärder och funktioner i Q#, som möjliggör kontrollflöden på högre nivå genom att förbli oberoende av specifika typer av indata/utdata, samt att *låna* kvantbitar. 
    Det senare skiljer sig från grundläggande kvantbitsallokering i och med att en Q#-åtgärd kan använda ”felaktiga” kvantbitar – dvs. kvantbitar som inte nödvändigtvis initierats till ett känt tillstånd – som hjälp vid beräkningar.

- I [Testa och felsöka](xref:microsoft.quantum.techniques.testing-and-debugging) beskrivs vissa tekniker där du kan kontrollera att din kod gör det den ska. 
    På grund av den övergripande komplexiteten i kvantinformation, kan det krävas särskilda tekniker när kvantprogram ska felsökas. 
    Lyckligtvis stöder Q# många av de klassiska felsökningstekniker som programmerare brukar använda, samt även de som är kvantspecifika. Detta innefattar att skapa/köra enhetstester i Q#, bädda in *kontroller* av värden och sannolikheter i koden, samt `Dump`-funktioner som visar status för måldatorn. 
    Den senare kan användas tillsammans med vår simulator med fullständigt tillstånd till att felsöka vissa delar av beräkningarna genom att kringgå vissa kvantbegränsningar (t.ex. ”no-cloning theorem”).


![Quantum](~/media/mobius_strip_preview.png)
