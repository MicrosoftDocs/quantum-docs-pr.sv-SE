---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799150"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installera Microsoft Quantum Development Kit (QDK)

Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering. QDK består av:

- programmeringsspråket Q#
- en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#
- ett värdprogram (skrivet i Python eller ett .NET-språk) som kör kvantåtgärder som har skrivits i Q#
- verktyg som underlättar ditt utvecklingsarbete

Beroende på din valda utvecklingsmiljö finns det olika installationssteg. Välj din miljö i avsnitten nedan.

## <a name="develop-with-python"></a>Utveckla med Python

Med qsharp-paketet för Python är det enkelt att simulera åtgärder och funktioner i Q# inifrån Python. IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.

1. Förutsättningar

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare
    - [.NET Core SDK 3.0 eller senare](https://www.microsoft.com/net/download)

1. Installera `qsharp`-paketet

    ```bash
    pip install qsharp
    ```

1. Installera `iqsharp`-paketet

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Skapa ett Python-program med namnet `hello_world.py` som anropar åtgärden `SayHello()` Q#:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Kör programmet:

        ```bash
        python hello_world.py
        ```

    - Verifiera utdata. Följande rader ska visas av programmet:

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Utveckla med Jupyter Notebook

Jupyter Notebook är en favorit för akademiska inställningar, vetenskapliga labbuppgifter och onlinebaserad samverkande programmering med kodkörning lokalt – nu inklusive Q#-kod – tillsammans med instruktioner, kommentarer och annat innehåll.  Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.

IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.


1. Förutsättningar

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 eller senare](https://www.microsoft.com/net/download)

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

    - Bläddra till den URL som visas på kommandoraden. Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Kör följande Notebook-cell:

        ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

        Du bör se `SayHello` i cellens utdata. När du använder Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.


    - I en ny cell simulerar du körningen i en kvantdator för den åtgärd som du nyss skapade med hjälp av `%simulate`-magic:

        ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

        Du bör se meddelandet på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet är det tomt).


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Utveckla med C# i Windows med Visual Studio

I Visual Studio finns en omfattande miljö för att utveckla Q#-program, med fantastiska funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.  Q# Visual Studio-tillägget innehåller mallar för Q#-filer och projekt samt syntaxmarkering och stöd för IntelliSense.


1. Förutsättningar

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat

1. Installera Q# Visual Studio-tillägget

    - Ladda ned [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Lägg till tillägget i Visual Studio

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa ett nytt Q#-program

        - Gå till **Arkiv** -> **Nytt** -> **Projekt**
        - Skriv `Q#` i sökrutan
        - Välj **Q#-program**
        - Välj **Nästa**
        - Välj ett namn och en plats för ditt program
        - Välj **Skapa**

    - Inspektera projektet

        Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.

    - Köra programmet

        - Välj **Felsökning** -> **Starta utan felsökning**
        - Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.

> [!NOTE]
> * Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.  

## <a name="develop-with-c-using-visual-studio-code"></a>Utveckla med C# och Visual Studio Code

I Visual Studio Code (VS Code) finns en omfattande miljö för att utveckla Q#-program i många olika datormiljöer, bland annat Windows, Linux och Mac. Det finns även användningsbara funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.  Q# VS Code-tillägget innehåller syntaxmarkering och Q#-kodfragment.

1. Förutsättningar

   - [VS-kod](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 eller senare](https://www.microsoft.com/net/download)

1. Installera Quantum VS Code-tillägget

    - Installera [VS Code-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Installera Quantum-projektmallarna:

   - Gå till **Visa** -> **Kommandopaletten**
   - Välj **Q#: Installera projektmallar**

    Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa ett nytt projekt:

        - Gå till **Visa** -> **Kommandopaletten**
        - Välj **Q#: Skapa nytt projekt**
        - Gå till den plats i filsystemet där du vill skapa programmet
        - Klicka på knappen **Öppna nytt projekt...** när projektet har skapats

    - Kör programmet:

        - Gå till **Felsökning** -> **Starta utan felsökning**
        - Du bör se följande text i utdatafönstret `Hello quantum world!`

> [!NOTE]
> * > * Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Utveckla med C# med hjälp av kommandoradsverktyget `dotnet`

Naturligtvis kan du också skapa och köra Q#-program från kommandoraden, genom att helt enkelt installera .NET Core SDK och QDK-projektmallarna. 

1. Förutsättningar

    - [.NET Core SDK 3.0 eller senare](https://www.microsoft.com/net/download)

1. Installera kvantprojektmallar för .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa ett nytt program

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Gå till den nya programkatalogen

       ```bash
       cd runSayHello
       ```

    Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).

    - Köra programmet

        ```bash
        dotnet run
        ```

        Du bör se följande utdata: `Hello quantum world!`

## <a name="whats-next"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).
