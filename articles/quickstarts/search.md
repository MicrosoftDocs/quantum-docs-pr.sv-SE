---
title: Kör Grovers sökalgoritm i Q# – Quantum Development Kit
description: Skapa ett Q#-projekt som visar Grovers algoritm, en av de legendariska kvantalgoritmerna.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 9e4c53b4d5159cf07f0654603c1d477ad09eb7c6
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327415"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Självstudier: Implementera Grovers sökalgoritm i Q\#

I den här självstudien lär du dig att skapa och köra Grover-sökning som påskyndar sökningen i ostrukturerade data.  Grovers sökning är en av de mest populära kvantberäkningsalgoritmerna. Den här relativt lilla Q#-implementeringen ger dig en uppfattning om några av fördelarna med programmering av kvantlösningar med kvantprogrammeringsspråket Q# som på hög nivå uttrycker kvantalgoritmer.  I slutet av guiden kommer du att se att simuleringen hittar en specifik sträng i listan med osorterade poster på en bråkdel av den tid det skulle ta att söka igenom hela listan på en klassisk dator.

Grovers algoritm söker i en lista med ostrukturerade data efter vissa objekt. Den kan till exempel svara på frågan: Är det här kortet som drogs ur en kortlek hjärter ess? Märkningen av det speciella objektet kallas för _markerad indata_.

Med hjälp av Grovers sökalgoritm kommer kvantdatorn garanterat att utföra sökningen i färre steg än antalet objekt i listan som du söker i, något som inte kan göras av en klassisk algoritm. Den ökade hastigheten när en kortlek ska genomsökas är försumbar, men i listor som innehåller miljontals eller miljardtals objekt blir det mer viktigt.

Du kan bygga Grovers sökalgoritm med bara några rader kod.

## <a name="prerequisites"></a>Krav

- Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Vad gör Grovers sökalgoritm?

Grovers algoritm frågar om ett objekt i en lista är det som vi söker efter. Detta görs genom att en kvantsuperposition skapas av indexen i listan med respektive koefficient, eller sannolikhetsamplitud, vilket utgör sannolikheten för att det aktuella indexet är det som du söker efter.

Algoritmen består av två steg som ökar indexkoefficienten som vi söker efter inkrementellt, fram till att sannolikhetsamplituden för den aktuella koefficienten blir ett.

Antalet stegvisa ökningar är färre än antalet objekt i listan. Det här är anledningen till att Grovers sökalgoritm utför sökningen i färre steg än en klassisk algoritm.

![Funktionsdiagram över Grovers sökalgoritm](~/media/grover.png)

## <a name="write-the-code"></a>Skriva koden

1. Använd Quantum Development Kit för att [skapa ett nytt Q#-projekt för kommandoradsprogrammet](xref:microsoft.quantum.install.standalone). Ge projektet rubriken `Grover`.

1. I projektfilen `Program.qs` lägger du till följande kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Definiera listan som vi söker i genom att skapa den nya filen `Reflections.qs` där du klistrar in följande kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Åtgärden `ReflectAboutMarked` definierar den markerade indata som du söker efter: Strängen med alternerande nollor och ettor. I det här exemplet hårdkodas markerad indata, vilket kan utökas till att söka efter olika indata eller generaliseras för alla indata.

1. Kör sedan ditt nya Q#-program för att hitta objektet som markerats med `ReflectAboutMarked`.

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Q#-kommandoradsprogram med Visual Studio eller Visual Studio Code

Den körbara filen kör åtgärden eller funktionen som har markerats med attributet `@EntryPoint()` i en simulator eller i ett resursuppskattningsverktyg, beroende på projektkonfigurationen och kommandoradsalternativen.

Tryck bara på Ctrl+F5 i Visual Studio för att köra skriptet.

Skapa `Program.qs` första gången genom att skriva följande i terminalfönstret i VS Code:

```Command line
dotnet build
```

För efterföljande körningar behöver du inte bygga det igen. Du kör det bara genom att skriva följande kommando och trycka på Retur:

```Command line
dotnet run --no-build
```

Följande meddelande bör visas i terminalfönstret:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Det beror på att du inte angav hur många kvantbitar du ville använda. Därför visar terminalfönstret vilka kommandon som är tillgängliga för den körbara filen Om vi vill använda fem kvantbitar skriver vi:

```Command line
dotnet run --n-qubits 5
```

När du trycker på Retur bör du se följande utdata:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Nästa steg

Om du gillade den här självstudien kan du använda resurserna nedan för att lära dig mer om hur du använder Q# för att skriva egna kvantprogram:

- [Tillbaka till guiden Komma igång med QDK](xref:microsoft.quantum.welcome)
- Prova en mer allmän Grover-sökalgoritm [exempel](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)
- [Läs mer om Grovers sökning med Quantum Katas](xref:microsoft.quantum.overview.katas)
- Läs mer om [Amplitudförstärkning][amplitude-amplification], kvantberäkningstekniken bakom Grovers sökalgoritm
- [Begrepp inom kvantberäkning](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit-exempel](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
