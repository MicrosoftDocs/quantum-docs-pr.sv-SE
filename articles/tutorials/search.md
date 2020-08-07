---
title: Kör Grover Sök algoritm i Q# Quantum Development Kit
description: Bygg ett Q# projekt som demonstrerar Grover-algoritmen, en av de kanoniska Quantum-algoritmerna.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c23d71209eb484a510f102e8b581ba4ec21829a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869672"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Självstudier: Implementera Grovers sökalgoritm i Q\#

I den här självstudien lär du dig att skapa och köra Grover-sökning som påskyndar sökningen i ostrukturerade data.  Grover: s sökning är en av de mest populära Quantum Computing-algoritmerna, och den här relativt små Q# implementeringen ger dig en uppfattning om några av fördelarna med programmering av Quantum-lösningar med ett högnivå Q# Quantum programmeringsspråk för att uttrycka Quantum-algoritmer.  I slutet av guiden kommer du att se att simuleringen hittar en specifik sträng i listan med osorterade poster på en bråkdel av den tid det skulle ta att söka igenom hela listan på en klassisk dator.

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

1. [Skapa ett nytt Q# projekt för kommando rads programmet](xref:microsoft.quantum.install.standalone)med hjälp av Quantum Development Kit. Ge projektet rubriken `Grover`.

1. I projektfilen `Program.qs` lägger du till följande kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Definiera listan som vi söker i genom att skapa den nya filen `Reflections.qs` där du klistrar in följande kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Åtgärden `ReflectAboutMarked` definierar den markerade indata som du söker efter: Strängen med alternerande nollor och ettor. I det här exemplet hårdkodas markerad indata, vilket kan utökas till att söka efter olika indata eller generaliseras för alla indata.

1. Kör sedan det nya Q# programmet för att hitta objektet som marker ATS av `ReflectAboutMarked` .

### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Q#kommando rads program med Visual Studio eller Visual Studio Code

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

Om du gillade den här själv studie kursen kan du läsa mer om hur du kan använda Q# för att skriva egna Quantum-program på några av resurserna nedan.

- [Tillbaka till guiden Komma igång med QDK](xref:microsoft.quantum.welcome)
- Prova en mer allmän Grover-sökalgoritm [exempel](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)
- [Läs mer om Grovers sökning med Quantum Katas](xref:microsoft.quantum.overview.katas)
- Läs mer om [Amplitudförstärkning][amplitude-amplification], kvantberäkningstekniken bakom Grovers sökalgoritm
- [Begrepp inom kvantberäkning](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit-exempel](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
