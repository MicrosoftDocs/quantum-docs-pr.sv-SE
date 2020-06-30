---
title: Utveckla med Q# Jupyter Notebooks
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274159"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Utveckla med Q# Jupyter Notebooks

Installera QDK för utveckling av Q#-åtgärder i Q# Jupyter Notebooks.

Jupyter Notebooks innehåller kodkörning på plats, samt instruktioner, kommentarer och annat innehåll. Den här miljön är idealisk när du vill skriva Q#-kod med inbäddade förklaringar eller skapa interaktiva självstudier för kvantberäkning. Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.

IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.

> [!NOTE]
> * I Q# Jupyter Notebooks kan du bara köra Q#-kod och åtgärderna kan inte anropas från externa värdprogram (t.ex. Python- eller C#-filer). Miljön är inte lämplig om målet är att kombinera ett externt klassiskt värdprogram med kvantprogrammet.

1. Krav

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installera `iqsharp`-paketet

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Om du får ett felmeddelande under `dotnet iqsharp install`-steget, öppnar du ett nytt terminalfönster och försöker igen.
    > Om det fortfarande inte fungerar kan du försöka hitta det installerade `dotnet-iqsharp`-verktyget (i Windows, `dotnet-iqsharp.exe`) och köra:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > där `/path/to/dotnet-iqsharp` ersätts med den absoluta sökvägen till `dotnet-iqsharp`-verktyget i filsystemet.
    > Den finns vanligtvis under `.dotnet/tools` i användarprofilens mapp.

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Kör följande kommando för att starta Notebook-servern:

        ```
        jupyter notebook
        ```

    - Öppna Jupyter Notebook genom att kopiera och klistra in webbadressen som finns på kommandoraden i webbläsaren.

    - Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Kör följande Notebook-cell:

        ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

        Du bör se `SayHello` i cellens utdata. När du kör Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.


    - I en ny cell kör du den åtgärd som du nyss skapade (i en simulator) med kommandot `%simulate`:

        ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

        Du bör se meddelandet på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet ser vi den tomma tuppeln `()` eftersom åtgärden returnerar en `Unit`-typ).

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat QDK för Q# Jupyter Notebooks kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng) genom att skriva Q#-kod direkt i Jupyter Notebook-miljön.

Fler exempel på vad du kan göra med Q# Jupyter Notebooks finns i:
- [Introduktion till Q# och Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Där finns en Q# Jupyter Notebook som visar hur du använder Q# i den här miljön.
- [Quantum Katas](xref:microsoft.quantum.overview.katas) är en samling självstudier och uppsättningar med programmeringsövningar med öppen källkod i form av Q# Jupyter Notebooks. Det kan vara bra att börja med [Quantum Katas-självstudiernas notebook-filer](https://github.com/microsoft/QuantumKatas#tutorial-topics). I Quantum Katas lär du dig både kvantberäkning och Q#-programmering på samma gång. De är ett utmärkt exempel på den typ av innehåll du kan skapa med Q# Jupyter Notebooks.
