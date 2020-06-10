---
title: 'Utveckla med Q # och python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630291"
---
# <a name="develop-with-q-and-python"></a>Utveckla med Q # och python

Installera QDK för att utveckla python-värdprogram för att anropa Q #-åtgärder.

1. Krav

    - [Python](https://www.python.org/downloads/) 3.6 eller senare
    - [PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installera `qsharp` paketet, ett python-paket som aktiverar interop mellan Q # och python.

    ```
    pip install qsharp
    ```

1. Installera SWEETIQ #, en kernel som används av Jupyter och python och som tillhandahåller grundläggande funktioner för att kompilera och köra frågor i Q #.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Om du får ett fel under `dotnet iqsharp install` steget öppnar du ett nytt terminalfönster och försöker igen.
    > Om det fortfarande inte fungerar kan du försöka hitta det installerade `dotnet-iqsharp` verktyget (i Windows `dotnet-iqsharp.exe` ) och köra:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > var `/path/to/dotnet-iqsharp` bör ersättas av den absoluta sökvägen till `dotnet-iqsharp` verktyget i fil systemet.
    > Detta är vanligt vis under `.dotnet/tools` i mappen användar profil.
  
1. Även om du kan använda Q # med python i en IDE, rekommenderar vi starkt att du använder Visual Studio Code (VS Code) IDE för dina Q # + python-program. Genom att använda Visual Studio Code och QDK Visual Studio Code-tillägget får du till gång till mer avancerade funktioner.

    - Installera [vs Code](https://code.visualstudio.com/download) (Windows, Linux och Mac)
    - Installera [QDK-tillägget för vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

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
> * Du kan också använda python Jupyter Notebooks för att skriva det klassiska python-programmet och anropa Q #-åtgärder från cellerna. Python-koden är bara ett vanligt python-program.

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
