---
title: Kör Grovers sökalgoritm i Q# – Quantum Development Kit
description: Skapa ett Q#-projekt som visar Grovers algoritm, en av de legendariska kvantalgoritmerna.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906958"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Snabbstart: Implementera Grovers sökalgoritm i Q#

I den här snabbstarten får du lära dig att skapa och köra Grover-sökning som påskyndar sökningen i ostrukturerade data.  Grovers sökning är en av de mest populära kvantberäkningsalgoritmerna. Den här relativt lilla Q#-implementeringen ger dig en uppfattning om några av fördelarna med programmering av kvantlösningar med kvantprogrammeringsspråket Q# som på hög nivå uttrycker kvantalgoritmer.  I slutet av guiden kommer du att se att simuleringen hittar en specifik sträng i listan med osorterade poster på en bråkdel av den tid det skulle ta att söka igenom hela listan på en klassisk dator.

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

1. Med hjälp av Quantum Development Kit [skapas ett nytt Q#-projekt](xref:microsoft.quantum.howto.createproject) som kallas `Grover` i valfri utvecklingsmiljö.

1. I projektfilen `Operations.qs` lägger du till följande kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. Definiera listan som vi söker i genom att skapa den nya filen `Reflections.qs` där du klistrar in följande kod:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Åtgärden `ReflectAboutMarked` definierar den markerade indata som du söker efter: Strängen med alternerande nollor och ettor. I det här exemplet hårdkodas markerad indata, vilket kan utökas till att söka efter olika indata eller generaliseras för alla indata.

1. Kör sedan ditt nya Q#-program för att hitta objektet som markerats med `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python med Visual Studio Code eller kommandoraden](#tab/tabid-python)

    Om du vill köra ditt nya Q#-program från Python sparar du följande kod som `host.py`:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Du kan sedan köra Python-värdprogrammet från kommandoraden:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# med Visual Studio Code eller kommandoraden](#tab/tabid-csharp)

    Om du vill köra ditt nya Q#-program från C# ändrar du `Driver.cs` så att följande C#-kod ingår:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Du kan sedan köra C#-värdprogrammet från kommandoraden:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# med Visual Studio 2019](#tab/tabid-vs2019)

    Om du vill köra ditt nya Q#-program från C# i Visual Studio ändrar du `Driver.cs` så att följande C#-kod ingår:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Därefter trycker du på F5. Programmet startas och ett nytt fönster med följande resultat visas: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    Åtgärden `ReflectAboutMarked` anropades bara fyra gånger, men ditt Q#-program hittade indatan ”01010” bland $2^{5} = 32$ möjliga indata!

## <a name="next-steps"></a>Nästa steg

Om du gillade den här snabbstarten kan du titta närmare på några av resurserna nedan, där du lär dig mer om hur du kan använda Q# för att skriva egna kvantprogram:

- [Tillbaka till guiden Komma igång med QDK](xref:microsoft.quantum.welcome)
- Prova en mer allmän Grover-sökalgoritm [exempel](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)
- [Läs mer om Grovers sökning med Quantum Katas](xref:microsoft.quantum.overview.katas)
- Läs mer om [Amplitudförstärkning](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), kvantberäkningstekniken bakom Grovers sökalgoritm
- [Begrepp inom kvantberäkning](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit-exempel](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
