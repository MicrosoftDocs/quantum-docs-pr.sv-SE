---
title: Utveckla med Q#-kommandoradsprogram
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274194"
---
# <a name="develop-with-q-command-line-applications"></a>Utveckla med Q#-kommandoradsprogram

Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python.

## <a name="prerequisites"></a>Krav

- [.NET Core SDK 3.1 eller senare](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Även om du kan skapa Q#-kommandoradsprogram i vilken IDE som helst, rekommenderar vi att du använder IDE:n för Visual Studio Code (VS Code) eller Visual Studio till dina Q#-program. Utveckling med dessa verktyg ger tillgång till omfattande funktioner.

Konfigurera VS Code:

1. Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).
2. Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Konfigurera Visual Studio:

1. Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.
2. Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Utveckla i C# med VS Code

Installera Q#-projektmallarna:

1. Öppna VS Code.
2. Klicka på **Visa** -> **Kommandopalett**.
3. Välj **Q#: Installera projektmallar**.

När **Projektmallar har installerats** visas, kan QDK:n användas med dina egna program och bibliotek.

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

## <a name="develop-with-q-using-visual-studio"></a>Utveckla med Q# och Visual Studio

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


## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
