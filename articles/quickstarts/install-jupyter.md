---
title: Utveckla med Q# Jupyter Notebooks
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 8a878e8f930f4b898f4de35751e4a39cc8716cec
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884269"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Utveckla med Q# Jupyter Notebooks

Installera QDK för utveckling av Q#-åtgärder i Q# Jupyter Notebooks.

Jupyter Notebooks innehåller kodkörning på plats, samt instruktioner, kommentarer och annat innehåll. Den här miljön är idealisk när du vill skriva Q#-kod med inbäddade förklaringar eller skapa interaktiva självstudier för kvantberäkning. Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.

> [!NOTE]
> * I Q# Jupyter Notebooks kan du bara köra Q#-kod, och åtgärderna kan inte anropas från externa värdprogram (till exempel Python- eller C#-filer). Miljön är inte lämplig om målet är att kombinera ett externt klassiskt värdprogram med kvantprogrammet.

## <a name="install-the-iq-jupyter-kernel"></a>Installera Q# Jupyter-kärnan

IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.

### <a name="install-using-conda-recommended"></a>[Installera med hjälp av conda (rekommenderas)](#tab/tabid-conda)

1. Installera [Miniconda](https://docs.conda.io/en/latest/miniconda.html) eller [Anaconda](https://www.anaconda.com/products/individual#Downloads).

1. Öppna en Anaconda-prompt.

   - Eller om du föredrar att använda PowerShell eller pwsh: öppna ett gränssnitt, kör `conda init powershell`, stäng och öppna sedan gränssnittet igen.

1. Skapa och aktivera en ny conda-miljö som heter `qsharp-env` med de nödvändiga paketen (inklusive Jupyter Notebook och IQ#) genom att köra följande kommandon:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Kör `python -c "import qsharp"` från samma terminal för att verifiera installationen och fylla i det lokala paketets cacheminne med alla nödvändiga QDK-komponenter.

### <a name="install-using-net-cli-advanced"></a>[Installera med hjälp av .NET CLI (avancerat)](#tab/tabid-dotnetcli)

1. Krav:

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installera `Microsoft.Quantum.IQSharp`-paketet.

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
    
***

Klart! Nu har du IQ#-kärnan för Jupyter, som tillhandahåller grundläggande funktioner för kompilering och körning av Q#-åtgärder från Q# Jupyter Notebooks.

## <a name="create-your-first-q-notebook"></a>Skapa din första Q#-notebook

Nu är du redo att verifiera installationen av Q# Jupyter Notebook genom att skriva och köra en enkel Q#-åtgärd.

1. Från den miljö som du skapade under installationen (det vill säga antingen den conda-miljö som du skapade eller den Python-miljö där du installerade Jupyter) kör du följande kommando för att starta Jupyter Notebook-servern:

    ```
    jupyter notebook
    ```

    - Om Jupyter Notebook inte öppnas automatiskt i webbläsaren kopierar och klistrar du in den URL som finns på kommandoraden till webbläsaren.

1. Välj ”Ny” → ”Q#” för att skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Kör följande Notebook-cell:

    ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

    Du bör se `SampleQuantumRandomNumberGenerator` i cellens utdata. När du kör Jupyter Notebook kompileras Q#-koden och cellen visar namnet på eventuella åtgärder som den hittar.

1. I en ny cell kör du den åtgärd som du nyss skapade (i en simulator) med kommandot `%simulate`:

    ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

    Du bör se resultatet av den åtgärd du anropade. Eftersom åtgärden genererar ett slumpmässigt resultat visas i det här fallet antingen `Zero` eller `One` på skärmen. Om du kör cellen upprepade gånger bör du se varje resultat ungefär varannan gång.

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat QDK för Q# Jupyter Notebooks kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng) genom att skriva Q#-kod direkt i Jupyter Notebook-miljön.

Fler exempel på vad du kan göra med Q# Jupyter Notebooks finns i:

- [Introduktion till Q# och Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Där finns en Q# Jupyter Notebook med mer information om hur du använder Q# i Jupyter-miljön.
- [Quantum Katas](xref:microsoft.quantum.overview.katas) är en samling självstudier och uppsättningar med programmeringsövningar med öppen källkod i form av Q# Jupyter Notebooks. Det kan vara bra att börja med [Quantum Katas-självstudiernas notebook-filer](https://github.com/microsoft/QuantumKatas#tutorial-topics). I Quantum Katas lär du dig både kvantberäkning och Q#-programmering på samma gång. De är ett utmärkt exempel på den typ av innehåll du kan skapa med Q# Jupyter Notebooks.
