---
title: Grundläggande klassificering med Quantum Machine Learning-biblioteket
description: 'Lär dig hur du kör en Quantum-följd som skrivits i Q # med Quantum Machine Learning-biblioteket för Microsoft-QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275790"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Grundläggande klassificering: klassificera data med QDK

I den här snabb starten får du lära dig hur du kör en Quantum-följd som skrivits i Q # med Quantum Machine Learning-biblioteket för QDK. 

I den här hand boken kommer vi att använda den halva måne-datauppsättningen med en klassificerings struktur som definierats i Q #.

## <a name="prerequisites"></a>Krav

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Skapa ett Q #-projekt för antingen ett [python-värdprogram](xref:microsoft.quantum.install.python) eller [C#-värd program](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Värd program

Ditt värd program består av tre delar:

- Läs in data uppsättningen och välj en uppsättning start parametrar för din modell.
- Kör träning för att fastställa modellens parametrar och förskjutning.
- Validera modellen för att fastställa dess exakthet

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python med Visual Studio Code eller kommandoraden](#tab/tabid-python)

    Om du vill köra är du Q #-klassificeraren från python och sparar följande kod som `host.py` . Kom ihåg att du även behöver den Q #-fil `Training.qs` som beskrivs senare i den här självstudien.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Du kan sedan köra Python-värdprogrammet från kommandoraden:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# med Visual Studio Code eller kommandoraden](#tab/tabid-csharp)

    Om du vill köra är du Q # klassificerare från C# och sparar följande kod som `Host.cs` . Kom ihåg att du även behöver den Q #-fil `Training.qs` som beskrivs senare i den här självstudien.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Du kan sedan köra C#-värdprogrammet från kommandoraden:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# med Visual Studio 2019](#tab/tabid-vs2019)

    Om du vill köra ditt nya Q #-program från C# i Visual Studio ändrar `Host.cs` du till att inkludera följande C#-kod. Kom ihåg att du även behöver den Q #-fil `Training.qs` som beskrivs senare i den här självstudien.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Därefter trycker du på F5. Programmet startas och ett nytt fönster med följande resultat visas: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q- \# klassificerings kod

Nu ska vi se hur de åtgärder som anropas av värd programmet definieras i Q #.
Vi sparar följande kod i en fil med namnet `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

De viktigaste funktionerna och åtgärderna som definieras i koden ovan är:

- `ClassifierStructure() : ControlledRotation[]`: i den här funktionen ställer vi in strukturen för vår krets modell genom att lägga till lagren i de kontrollerade portar som vi anser. Det här steget är detsamma som deklarationen av lager i neurons i en sekventiell djup inlärnings modell.
- `TrainHalfMoonModel() : (Double[], Double)`: den här åtgärden är den grundläggande delen av koden och definierar utbildningen. Här läser vi in exemplen från data uppsättningen som ingår i biblioteket, vi ställer in Hyper-parametrarna och de ursprungliga parametrarna för utbildningen och vi startar utbildningen genom att anropa åtgärden som `TrainSequentialClassifier` ingår i biblioteket. Den matar ut parametrarna och den förskjutning som avgör klassificeraren.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: den här åtgärden definierar verifierings processen för att utvärdera modellen. Här läser vi in exemplen för verifiering, antalet mätningar per prov och toleransen. Den ger ut antalet felklassificeringar för den valda batchen över exempel för verifiering.

## <a name="next-steps"></a>Nästa steg

Först kan du spela med koden och försöka ändra vissa parametrar för att se hur den påverkar utbildningen. I nästa självstudie utformar du sedan [din egen klassificerare](xref:microsoft.quantum.libraries.machine-learning.design)och du får lära dig hur du definierar klassificerarens struktur.