---
title: 'Utveckla med Q # Jupyter-anteckningsböcker'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551047"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Utveckla med Q # Jupyter-anteckningsböcker

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

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Kör följande kommando för att starta Notebook-servern:

        ```bash
        jupyter notebook
        ```

    - Öppna Jupyter Notebook-kopian och klistra in den URL som tillhandahålls av kommando raden i webbläsaren.

    - Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Kör följande Notebook-cell:

        ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

        Du bör se `SayHello` i cellens utdata. När du använder Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.


    - I en ny cell kör du åtgärden som du nyss skapade (i en simulator) genom att använda `%simulate` kommandot:

        ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

        Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (här ser vi den tomma tuppeln `()` eftersom vår åtgärd bara returnerar en `Unit` typ).

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
