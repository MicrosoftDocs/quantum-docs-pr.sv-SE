---
title: Utveckla med Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577828"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Utveckla med Q# Jupyter Notebooks

Installera QDK för utveckling av Q #-åtgärder på Q # Jupyter Notebooks.

Jupyter Notebooks möjliggör kod körning på plats tillsammans med instruktioner, kommentarer och annat innehåll. Den här miljön är idealisk för att skriva Q # Code med inbäddade förklaringar eller interaktiva självstudier. Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.

IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.

> [!NOTE]
> * I Q # Jupyter Notebooks kan du bara köra Q # Code, och åtgärderna kan inte anropas från externa värd program (t. ex. python-eller C#-filer). Den här miljön är inte lämplig om målet är att kombinera ett externt klassiskt värd program med Quantum-programmet.

1. Förutsättningar

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installera `iqsharp`-paketet

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Kör följande kommando för att starta Notebook-servern:

        ```
        jupyter notebook
        ```

    - Om du vill öppna Jupyter Notebook kopierar du och klistrar in webb adressen som tillhandahålls av kommando raden i webbläsaren.

    - Skapa en Jupyter Notebook med en Q #-kernel och Lägg till följande kod i den första notebook-cellen:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Kör följande Notebook-cell:

        ![Jupyter Notebook cell med Q # Code](~/media/install-guide-jupyter.png)

        Du bör se `SayHello` i cellens utdata. När du kör i Jupyter Notebook kompileras Q #-koden och antecknings boken visar namnet på den eller de åtgärder som den hittar.


    - I en ny cell kör du åtgärden som du nyss skapade (i en simulator) genom att använda `%simulate` kommandot:

        ![Jupyter Notebook cell med% simulera Magic](~/media/install-guide-jupyter-simulate.png)

        Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (här ser vi den tomma tuppeln `()` eftersom vår åtgärd bara returnerar en `Unit` typ).

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat QDK för Q # Jupyter Notebooks kan du skriva och köra [ditt första Quantum-program](xref:microsoft.quantum.quickstarts.qrng) genom att skriva din Q #-kod direkt i Jupyter Notebooks miljön.

För fler exempel på vad du kan göra med Q # Jupyter notebooks, kan du ta en titt på:
- [Introduktion till Q # och Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Där hittar du ett Q #-Jupyter Notebook som visar hur du använder Q # i den här miljön.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), en samling med öppen källkod i självstudier och uppsättningar av programmerings övningar i form av Q # Jupyter Notebooks. [Datorerna i Quantum Katas-självstudier](https://github.com/microsoft/QuantumKatas#tutorial-topics) är en start punkt. Quantum Katas syftar till att lära dig element i Quantum data behandling och Q #-programmering på samma tidpunkt. De är ett utmärkt exempel på vilken typ av innehåll som du kan skapa med Q # Jupyter Notebooks.
