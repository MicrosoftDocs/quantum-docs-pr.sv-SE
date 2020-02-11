---
title: 'Utveckla med Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036295"
---
# <a name="develop-with-q--c"></a>Utveckla med Q # +C#

Installera QDK för att utveckla C# värd program för att anropa Q #-åtgärder.

Q # är utformat för att spela bra med .NET-språk – C#särskilt. Du kan arbeta med denna koppling i olika utvecklings miljöer:

- [Q # + C# använda Visual Studio (Windows)](#VS)
- [Q # + C# använda Visual Studio Code (Windows, Linux och Mac)](#VSC)
- [Q # + C# använda kommando rads verktyget `dotnet`](#command)

## Utveckla med Q # + C# med Visual Studio <a name="VS"></a>

Visual Studio erbjuder en omfattande miljö för att utveckla Q #-program. Q # Visual Studio-tillägget innehåller mallar för Q #-filer och-projekt samt markering av syntax, kod komplettering och stöd för IntelliSense.


1. Förutsättningar

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat

1. Installera Q# Visual Studio-tillägget

    - Ladda ned och installera [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

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

## Utveckla med Q # + C# med Visual Studio Code <a name="VSC"></a>

Visual Studio Code (VS Code) erbjuder en omfattande miljö för att utveckla Q #-program på Windows, Linux och Mac.  Q # VS Code-tillägget innehåller stöd för markering av Q #-syntax, kod komplettering och Q #-kodfragment.

1. Förutsättningar

   - [VS-kod](https://code.visualstudio.com/download)
   - [.NET Core SDK 3,1 eller senare](https://www.microsoft.com/net/download)

1. Installera Quantum VS Code-tillägget

    - Installera [VS Code-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Installera Quantum-projektmallarna:

   - Gå till **Visa** -> **Kommandopaletten**
   - Välj **Q #: installera projektmallar**

    Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa ett nytt projekt:

        - Gå till **Visa** -> **Kommandopaletten**
        - Välj **Q #: skapa nytt projekt**
        - Välj **fristående konsol program**
        - Gå till den plats i filsystemet där du vill skapa programmet
        - Klicka på knappen **Öppna nytt projekt...** när projektet har skapats

    - Om du inte redan har installerat C# tillägget vs Code visas ett popup-fönster. Installera tillägget. 

    - Kör programmet:

        - Gå till **terminal** -> **ny terminal**
        - Ange `dotnet run`
        - Du bör se följande text i utdatafönstret `Hello quantum world!`


> [!NOTE]
> * Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

## Utveckla med Q # + C# med hjälp av kommando rads verktyget `dotnet`<a name="command"></a>

Naturligtvis kan du också skapa och köra Q#-program från kommandoraden, genom att helt enkelt installera .NET Core SDK och QDK-projektmallarna. 

1. Förutsättningar

    - [.NET Core SDK 3,1 eller senare](https://www.microsoft.com/net/download)

1. Installera kvantprojektmallar för .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa ett nytt program

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - Gå till den nya programkatalogen

       ```bash
       cd runSayHello
       ```

    Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).

    - Köra programmet

        ```dotnetcli
        dotnet run
        ```

        Du bör se följande utdata: `Hello quantum world!`

    
## <a name="whats-next"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).
