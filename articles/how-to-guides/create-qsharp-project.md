---
title: 'Lär dig hur du skapar ett Q #-projekt med Quantum Development Kit (QDK)'
description: 'Initiera ett projekt för en Quantum-utveckling med QDK och Q # i den utvecklings miljö du väljer'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444182"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Skapa ett Q #-projekt i utvecklings miljön

Lär dig hur du skapar ett Q #-projekt med QDK.

Ett Q #-projekt innehåller Q #-filer som innehåller Quantum-kod, samt ett värd program för att köra programmet Quantum. Du kan skriva värd programmet i .NET-språk som C#, eller i python. Du kan också köra Q # Code i en Jupyter-anteckningsbok med SWEETIQ # kernel.

Välj utvecklings miljö och språk i avsnitten nedan:

* [Python](#create-a-python-project)
* [Jupyter-anteckningsböcker](#create-a-jupyter-notebook-project)
* [C#med Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#med VS Code](#create-a-c-project-using-vs-code)
* [C#med kommando raden](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Skapa ett python-projekt

1. Förutsättningar

     * [Quantum Development Kit för python](xref:microsoft.quantum.install#develop-with-python)

1. Skapa en mapp för ditt projekt och navigera till den mappen

1. Skapa en f #-fil med namnet `Operation.qs`och Lägg till din Q #-kod. Exempel:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Skapa en python-värd fil med namnet `host.py` för att anropa din Q #-åtgärd. Exempel:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Kör programmet:

    ```bash
    python host.py
    ```

1. Verifiera utdata. Följande rader ska visas av programmet:

    ```bash
    Hello from quantum world!
    0
    ```

Nu kan du fortsätta att utveckla ditt Quantum-program.

## <a name="create-a-jupyter-notebook-project"></a>Skapa ett Jupyter Notebook-projekt

1. Förutsättningar

    * [Quantum Development Kit för Jupyter Notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Kör följande kommando för att starta Notebook-servern:

    ```bash
    jupyter notebook
    ```

1. Bläddra till den URL som visas på kommandoraden. Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. En Jupyter-sida visas i webbläsaren. På fliken **filer** väljer du **nytt** > **Q #** för att skapa en Jupyter-anteckningsbok med en Q # kernel. Lägg till följande kod i den första notebook-cellen:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Markera **Cell** > **köra celler** för att köra antecknings boken. `SayHello` kommer snart att visas i cellens utdata:

    ![Jupyter Notebook-cell med Q # Code](~/media/install-guide-jupyter.png)

    När du kör i Jupyter-anteckningsböcker kompileras Q #-koden och antecknings boken visar namnet på den eller de åtgärder som den hittar.

1. I en ny cell simulerar du körningen i en Quantum-dator för den åtgärd som du nyss skapade med hjälp av `%simulate` Magic:

    ![Jupyter Notebook-cell med% simulera Magic](~/media/install-guide-jupyter-simulate.png)

    Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet tomt).

Nu kan du lägga till andra Q #-åtgärder för att fortsätta din Quantum-utveckling.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Skapa ett C# projekt i Windows med Visual Studio

1. Förutsättningar

    * [Quantum Development Kit för Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Skapa ett nytt Q#-program

    * Gå till **Arkiv** -> **Nytt** -> **Projekt**
    * Skriv `Q#` i sökrutan
    * Välj **Q#-program**
    * Välj **Nästa**
    * Välj ett namn och en plats för ditt program
    * Välj **Skapa**

1. Inspektera projektet

    Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.

1. Köra programmet

    * Välj **Felsökning** -> **Starta utan felsökning**
    * Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.

Nu kan du fortsätta med din Quantum-utveckling med Visual Studio

> [!NOTE]
> * Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.  

## <a name="create-a-c-project-using-vs-code"></a>Skapa ett C# projekt med vs Code

1. Förutsättningar

    * [Quantum Development Kit för vs Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Skapa ett nytt projekt:

    * Gå till **Visa** -> **Kommandopaletten**
    * Välj **Q #: skapa nytt projekt**
    * Gå till den plats i filsystemet där du vill skapa programmet
    * Klicka på knappen **Öppna nytt projekt...** när projektet har skapats

1. Kör programmet:

    * Gå till **Felsökning** -> **Starta utan felsökning**
    * Du bör se följande text i utdatafönstret `Hello quantum world!`

Nu kan du fortsätta med din Quantum-utveckling med Visual Studio Code.

> [!NOTE]
> * Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Skapa ett C# projekt med hjälp av kommando rads verktyget `dotnet`

1. Förutsättningar

    * [Quantum Development Kit för kommando raden](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

1. Skapa ett nytt program

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Gå till den nya programkatalogen

    ```bash
    cd <project name>
    ```

    Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).

1. Köra programmet

    ```bash
    dotnet run
    ```

    Du bör se följande utdata: `Hello quantum world!`

Nu kan du fortsätta med en Quantum-utveckling med hjälp av kommando rads verktyg.

## <a name="whats-next"></a>Vad står på tur?

Nu när du har skapat ett projekt i din önskade miljö kan du fortsätta med en Quantum-utveckling.
