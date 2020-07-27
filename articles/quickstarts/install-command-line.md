---
title: Utveckla med Q#-kommandoradsprogram
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871441"
---
# <a name="develop-with-q-command-line-applications"></a>Utveckla med Q#-kommandoradsprogram

Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python.

## <a name="prerequisites"></a>Krav

- [.NET Core SDK 3.1 eller senare](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Även om du kan skapa Q#-kommandoradsprogram i vilken IDE som helst, rekommenderar vi att du använder Visual Studio Code (VS Code) eller Visual Studio IDE när du utvecklar Q#-program lokalt. Vi rekommenderar att du använder Visual Studio Codespaces om du tänker utveckla i molnet via en webbläsare. Utveckling i dessa miljöer inbegriper de omfattande funktionerna i QDK-tillägget, däribland varningar, syntaxmarkeringar, projektmallar och mer. 

Konfigurera VS Code:

1. Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).
2. Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Konfigurera Visual Studio:

1. Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.
2. Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Så här konfigurerar du Visual Studio Codespaces:

1. Skapa ett [Azure-konto](https://azure.microsoft.com/free/).
2. Skapa en Codespaces-miljö. Följ [snabbstartsguiden](https://docs.microsoft.com/visualstudio/online/quickstarts/browser). När du skapar ett codespace rekommenderar vi att du anger `microsoft/Quantum` i fältet Git Repository (Git-lagringsplats) för att läsa in QDK-specifika inställningar.
3. Nu kan du starta din nya miljö och börja utveckla i webbläsaren via [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments). Du kan också använda en lokal installation av VS Code och använda Codespaces som en [fjärrmiljö](https://docs.microsoft.com/visualstudio/online/how-to/vscode).


Installera QDK för en annan miljö genom att ange följande på kommandoraden:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Utveckla med Q#

Följ anvisningarna på den flik som motsvarar din miljö.

### <a name="vs-code"></a>[VS-kod](#tab/tabid-vscode)

Skapa ett nytt projekt:

1. Klicka på **Visa** -> **Kommandopalett** och välj **Q#: Skapa nytt projekt**.
2. Klicka på **Fristående konsolprogram**.
3. Gå till platsen där du vill spara projektet och klicka på **Skapa projekt**.
4. När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.
        
Inspektera projektet. Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.

Så här kör du programmet:
1. Välj **Terminal** -> **Ny terminal**.
2. I terminalprompten anger du `dotnet run`.
3. Du bör se följande text i utdatafönstret `Hello quantum world!`


> [!NOTE]
> Arbetsytor med flera rotmappar stöds för närvarande inte av VS Code-tillägget för Q#. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Verifiera din Visual Studio-installation genom att skapa ett Q# `Hello World`-program.

Skapa ett nytt Q#-program:
1. Öppna Visual Studio och klicka på **Arkiv** -> **Nytt** -> **Projekt**.
2. Skriv `Q#` i sökrutan, välj **Q#-program** och klicka på **Nästa**.
3. Ange ett namn och en plats för programmet och klicka på **Skapa**.


Inspektera projektet. Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.

Så här kör du programmet:
1. Välj **Felsökning** -> **Starta utan felsökning**.
2. Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.

> [!NOTE]
> Om du har flera projekt i en Visual Studio-lösning, måste alla projekt i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.  

### <a name="other-editors-with-the-command-line"></a>[Andra redigeringsprogram med kommandoraden](#tab/tabid-cmdline)

Verifiera din installation genom att skapa ett Q# `Hello World`-program.

1. Installera projektmallarna.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

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
