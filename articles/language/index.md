---
title: Q#-programmeringsspråket | Microsoft Docs
description: Q#-programmeringsspråket
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035263"
---
# <a name="the-q-programming-language"></a>Q#-programmeringsspråket

# <a name="introduction"></a>Introduktion

En naturlig modell för kvantberäkning är att behandla kvantdatorn som en coprocessor, liknande den som används för GPU, FPGA och andra kompletterande processorer.
Den primära kontrollogiken kör en klassisk kod på en klassisk ”värddator”.
När det är lämpligt och nödvändigt kan värdprogrammet anropa en subrutin som körs på den kompletterande processorn.
När subrutinen är slutförd får värdprogrammet åtkomst till subrutinens resultat.

Q# (Q Sharp) är ett domänspecifikt programmeringsspråk som används till att uttrycka kvantalgoritmer.
Det används till att skriva subrutiner som körs på en kompletterande kvantprocessor, under kontroll av ett klassiskt värdprogram och en dator.
Innan kvantprocessorer är mer tillgängliga, körs Q#-subrutinerna på en simulator.

Q# innehåller en liten uppsättning primitiva typer, samt två sätt (matriser och tupplar) för att skapa nya, strukturerade typer.
Den har stöd för en grundläggande procedurmodell för att skriva program, med loopar och if/then-instruktioner.
De högsta nivåkonstruktionerna i Q# är användardefinierade typer, åtgärder och funktioner.

I följande avsnitt beskrivs:
- [Typmodellen](xref:microsoft.quantum.language.type-model)
- [Uttryck](xref:microsoft.quantum.language.expressions)
- [Instruktioner](xref:microsoft.quantum.language.statements)
- [Filstruktur](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a>Konventioner

Vi försöker säkerställa att vanliga skiljetecken används konsekvent i alla situationer.
Vi tänker oss att det blir enklare att lära sig Q# när dessa tecken alltid betyder samma sak, och att samma begrepp alltid representeras på samma sätt.

Mer specifikt:

- Semikolon, `;`, används för att avsluta en instruktion eller ett direktiv som bara består av en rad.
  Det används inte i något annat syfte.
- Kommatecknet, `,`, används till att avgränsa element i en sekvens. Det används för tuppelliteraler, matrisliteraler, argumentlistor, tuppeldefinitioner och typlistor. **I en ändring från tidigare versioner, stöds `;` inte längre som en matrisliteral avgränsare.**
- Kolontecknet, `:`, används för att inleda en typanteckning. Den används främst i anropningsbara signaturer.
  Eftersom kolontecknet alltid startar en typunderskrift, använder den tredelade villkorsstyrda operatorn som startas i 0,3 en lodrät stapel, `|`, till att avgränsa värden för sant och falskt. Det innebär att Q# använder `cond ? tval | fval` i stället för kolon som avgränsare på samma sätt som i C.
  
