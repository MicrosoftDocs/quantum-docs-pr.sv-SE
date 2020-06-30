---
title: Utveckla med Q# och Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274147"
---
# <a name="develop-with-q-and-python"></a>Utveckla med Q# och Python

Installera QDK:n om du vill utveckla Python-värdprogram som anropar Q#-åtgärder.

1. Krav

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
  
1. Även om du kan använda Q# med Python i en IDE, rekommenderar vi starkt att du använder IDE:n i Visual Studio Code (VS Code) till dina Q# + Python-program. När du använder Visual Studio Code och QDK-tillägget för Visual Studio Code, får du tillgång till fler funktioner.

    - Installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac)
    - Installera [QDK-tillägget för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Verifiera installationen genom att skapa ett `Hello World`-program

    - Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
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

        ```
        python hello_world.py
        ```

    - Verifiera utdata. Följande rader ska visas av programmet:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Du kan också använda Python Jupyter Notebooks till att skriva klassiska Python-program och anropa Q#-åtgärder från cellerna. Python-koden är bara ett vanligt Python-program.

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
