---
title: Introduktion till Quantum Development-metoder | Microsoft Docs
description: Introduktion till Quantum Development-metoder
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442564"
---
# <a name="q-program-overview"></a>Översikt över Q # program

Q # är ett skalbart, beskärmat programmeringsspråk för flera paradigm för Quantum Computing. Q # är ett Quantum-programmeringsspråk där det kan användas för att beskriva hur instruktioner körs på Quantum Machines. De datorer som kan vara riktade till den faktiska Quantum-maskinvaran. Q # är skalbart: det kan användas för att skriva enkla demonstrations program, t. ex. teleport som körs på några qubits, men som också har stöd för skrivning av stora, sofistikerade program som simulering av komplexa molekyler som kräver stora datorer med miljon tals qubits. Även om stora fysiska datorer fortfarande är i framtiden, tillåter Q # att en programmerare programmerar komplexa Quantum-algoritmer nu. Vad är mer, Q # stöder olika uppgifter som fel sökning, profilering, resurs uppskattning och vissa simuleringar av särskilda ändamål på ett skalbart sätt. 

Från ett tekniskt perspektiv kan ett Quantum-program ses som en viss uppsättning klassiska funktioner som, när de anropas, genererar Quantum-kretsar som deras sido effekter. En viktig följd av den vyn är att ett program som skrivits i Q # inte direkt modellerar qubits själva, utan beskriver i stället hur en klassisk kontroll dator interagerar med dessa qubits.
Enligt design definierar Q # alltså inte Quantum-tillstånd eller andra egenskaper för Quantum Mechanics direkt, utan i stället indirekt genom åtgärden för de olika under rutiner som definierats på språket.
Anta till exempel att State $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ beskrivs i instruktionen [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) .
För att förbereda detta tillstånd i Q #, använder vi de fakta som qubits initieras i $ \ket{0}$ State och att $ \ket{+} = H\ket{0}$, där $H $ är Hadamard-transformeringen:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # tranformations av Quantum-tillstånd

Det är viktigt att i Skriv programmet ovan inte uttryckligen referera till statusen inom Q #, utan att i stället se hur tillstånd har *omvandlats* av vårt program.
På samma sätt som när ett grafik shader-program samlar in en beskrivning av omvandlingar till varje hörn, ackumulerar ett Quantum-program i Q # omvandlingar till Quantum-tillstånd.
På så sätt kan vi helt oberoende om vad ett Quantum-tillstånd *är* även på varje måldator, vilket kan ha olika tolkningar beroende på datorn. 

Från perspektivet i ett Q #-program är en qubit en helt ogenomskinlig referens till den interna strukturen på mål datorn.
Ett Q #-program har ingen möjlighet att introspect en qubit, dess representation på en måldator, eller till och med om det är samma qubit som andra qubit som är tillgängliga för programmet.
Ett program kan istället anropa åtgärder som `Measure` för att lära sig information från en qubit och anropa åtgärder som `X` och `H` för att agera för en qubit.
Dessa åtgärder har ingen inbyggd definition på språket och görs konkreta enbart av mål datorn som används för att köra ett visst Q #-program.
Ett Q #-program kombinerar dessa åtgärder så som definieras av en mål dator för att skapa nya, högre åtgärder för att uttrycka Quantum-beräkning.
På så sätt gör Q # det enkelt att uttrycka logiken för de underliggande Quantum-och hybrid-klassiska algoritmerna, samtidigt som det är allmänt vad gäller strukturen för en mål dator eller Simulator.

## <a name="q-operations-and-functions"></a>Q #-åtgärder och-funktioner

Konkret, ett Q #-program består av en eller flera *åtgärder*, en eller flera *funktioner*och användardefinierade typer. Åtgärder används för att beskriva omvandlingar av status för en Quantum Machine och är de mest grundläggande Bygg stenarna för Q #-program. Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder, inklusive inbyggda *inbyggda åtgärder som* implementeras av en måldator.
När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.

Till skillnad från åtgärder används funktioner för att beskriva rent klassiskt beteende och har inga effekter, förutom att använda klassiska utmatnings värden. Q # är ett starkt skrivet språk och levereras med en uppsättning inbyggda primitiva typer samt stöd för användardefinierade typer. 

I resten av den här guiden kommer vi att se hur du använder olika språkkoncept och utformar för att hjälpa oss att definiera komplexa Quantum-program genom de grundläggande Bygg stenarna för åtgärder, funktioner och typer. 

## <a name="structure-of-q-source-files"></a>Struktur för Q # källfiler

En Q #-källfil består till minimalt av en *namn områdes deklaration*som anger ett .net-namn område som innehåller definitionerna i käll filen.
Definitioner från andra Q #-källfiler och-bibliotek kan inkluderas med hjälp av `open`-instruktionen.
Till exempel definieras de flesta av de åtgärder som definierar de grundläggande grindarna i namn området <xref:microsoft.quantum.intrinsic>.
För att göra detta tillgängligt för vår kod `open` vi bara det namn området överst i varje fil:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

I ett namn område kan varje Q #-källfil definiera en kombination av *åtgärder*, *funktioner*och *användardefinierade typer*.
I resten av det här avsnittet ska vi beskriva var och en i sin tur och tillhandahålla exempel på hur de kan användas i praktiken för att göra användbara Quantum-program.
