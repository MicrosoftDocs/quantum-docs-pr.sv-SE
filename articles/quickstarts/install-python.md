---
title: Utveckla med Q# och Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885541"
---
# <a name="develop-with-q-and-python"></a>Utveckla med Q# och Python

Installera QDK:n om du vill utveckla Python-värdprogram som anropar Q#-åtgärder.

## <a name="install-the-qsharp-python-package"></a>Installera Python-paketet `qsharp`

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

### <a name="install-using-net-cli-and-pip-advanced"></a>[Installera med hjälp av .NET CLI och pip (avancerat)](#tab/tabid-dotnetcli)

1. Krav:

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installera `qsharp`-paketet, vilket är ett Python-paket som ger interoperabilitet mellan Q# och Python.

    ```
    pip install qsharp
    ```

1. Installera IQ#, vilket är en kernel som främst används av Jupyter och Python och som innehåller grundläggande funktioner för att kompilera och köra Q#-åtgärder.

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

Klart! Nu har du både Python-paketet `qsharp` och IQ#-kärnan för Jupyter, som tillhandahåller grundläggande funktioner för kompilering och körning av Q#-åtgärder från Python samt ger möjlighet att använda Q# Jupyter Notebooks.

## <a name="choose-your-ide"></a>Välja IDE

Även om du kan använda Q# med Python i en IDE, rekommenderar vi starkt att du använder IDE:n i Visual Studio Code (VS Code) till dina Q# + Python-program. Med QDK Visual Studio Code-tillägget får du tillgång till omfattande funktioner såsom varningar, syntaxmarkeringar, projektmallar och mer.

Om du vill använda VS Code:

- Installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).
- Installera [QDK-tillägget för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Om du vill använda ett annat redigeringsprogram får du hjälp av anvisningarna ovan.

## <a name="write-your-first-q-program"></a>Skriva ditt första Q#-program

Nu är du redo att verifiera installationen av Python-paketet `qsharp` genom att skriva och köra ett enkelt Q#-program.

1. Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägga till följande kod i den:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. I samma mapp som `Operation.qs` skapar du ett Python-program som heter `host.py` för att simulera Q#-åtgärden `SampleQuantumRandomNumberGenerator()`:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. Från den miljö som du skapade under installationen (det vill säga den conda- eller Python-miljö där du installerade `qsharp`) kör du programmet:

    ```
    python host.py
    ```

1. Du bör se resultatet av den åtgärd du anropade. Eftersom åtgärden genererar ett slumpmässigt resultat visas i det här fallet antingen `Zero` eller `One` på skärmen. Om du kör programmet upprepade gånger bör du se varje resultat ungefär varannan gång.

> [!NOTE]
> * Python-koden är bara ett vanligt Python-program. Du kan använda valfri Python-miljö, däribland Python-baserade Jupyter Notebooks, för att skriva Python-programmet och anropa Q#-åtgärder. Python-programmet kan importera Q#-åtgärder från .qs-filer som finns i samma mapp som själva Python-koden.

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i önskad miljö kan du gå igenom den här självstudien för att skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
