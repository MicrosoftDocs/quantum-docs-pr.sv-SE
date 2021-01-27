---
title: Utveckla med Q#-program i en IDE
description: Lär dig hur du skapar ett Q#-program som körs från kommandotolken.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844322"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Utveckla med Q#-program i en IDE

Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python. Du kan utveckla Q#-program i Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces eller med valfritt redigeringsprogram/IDE-program och köra program från .NET-konsolen. 

## <a name="prerequisites-for-all-environments"></a>Krav för alla miljöer

- [.NET Core SDK 3.1 eller senare](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Även om du kan skapa Q#-program i vilken IDE som helst, rekommenderar vi att du använder Visual Studio Code (VS Code) eller Visual Studio IDE när du utvecklar Q#-program lokalt. Vi rekommenderar att du använder Visual Studio Codespaces om du tänker utveckla i molnet via en webbläsare. Utveckling i dessa miljöer använder de omfattande funktionerna i QDK-tillägget, däribland varningar, syntaxmarkeringar, projektmallar och mer. 

### <a name="to-configure-for-vs-code"></a>Konfigurera för VS Code:

1. Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).
2. Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

### <a name="to-configure-for-visual-studio"></a>Konfigurera för Visual Studio:

1. Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.
2. Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

### <a name="to-configure-for-another-environment"></a>Så här konfigurerar du för en annan miljö: 

1. Ange följande i kommandotolken

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Så här konfigurerar du för Visual Studio Codespaces:

1. Skapa ett [Azure-konto](https://azure.microsoft.com/free/).
2. Skapa en Codespaces-miljö. Följ [snabbstartsguiden](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). När du skapar ett codespace rekommenderar vi att du anger `microsoft/Quantum` i fältet Git Repository (Git-lagringsplats) för att läsa in QDK-specifika inställningar.
3. Nu kan du starta din nya miljö och börja utveckla i webbläsaren via [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments). Du kan också använda en lokal installation av VS Code och använda Codespaces som en [fjärrmiljö](https://docs.microsoft.com/visualstudio/online/how-to/vscode).

## <a name="develop-with-no-locq"></a>Utveckla med Q#

Följ anvisningarna i den flik som motsvarar din utvecklingsmiljö.

### <a name="vs-code"></a>[VS-kod](#tab/tabid-vscode)

Skapa ett nytt projekt:

1. Klicka på **Visa** -> **Kommandopalett** och välj **Q#: Skapa nytt projekt**.
2. Klicka på **Fristående konsolprogram**.
3. Gå till den plats där du vill spara projektet. Ange projektnamnet och klicka på **Skapa projekt**.
4. När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.

Inspektera projektet. Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.

Så här kör du programmet:

1. Välj **Terminal** -> **Ny terminal**.
2. I terminalprompten anger du `dotnet run`.
3. Du bör se följande text i utdatafönstret `Hello quantum world!`

> [!NOTE]
> Arbetsytor med flera rotmappar stöds för närvarande inte av VS Code-tillägget för Q#. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Verifiera din Visual Studio-installation genom att skapa ett Q#-program för `Hello World`.

Så här skapar du ett nytt Q#-program:

1. Öppna Visual Studio och klicka på **Arkiv** -> **Nytt** -> **Projekt**.
2. Skriv `Q#` i sökrutan, välj **Q#-program** och klicka på **Nästa**.
3. Ange ett namn och en plats för programmet och klicka på **Skapa**.


Inspektera projektet. Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.

Så här kör du programmet:

1. Välj **Felsökning** -> **Starta utan felsökning**.
2. Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.

> [!NOTE]
> Om du har flera projekt i en Visual Studio-lösning, måste alla projekt i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.  

### <a name="other-editors-with-the-command-prompt"></a>[Andra redigeringsprogram med kommandotolken](#tab/tabid-cmdline)

Verifiera din installation genom att skapa ett Q# `Hello World`-program.

1. Skapa ett nytt program:

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Gå till programkatalogen:

    ```dotnetcli
    cd runSayHello
    ```

    Den här katalogen bör du innehålla filen `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen. Du kan ändra den här mallen med ett textredigeringsprogram och skriva över den med dina egna kvantprogram. 

1. Kör programmet:

    ```dotnetcli
    dotnet run
    ```

1. Du bör se följande text skrivas ut: `Hello quantum world!`

***

## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
