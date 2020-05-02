---
title: 'Köra Q #-program utan en driv rutin och ett värd språk'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706809"
---
# <a name="q-command-line-applications"></a>Q # kommando rads program

Q #-program kan köras på egen hand utan en driv rutin på ett värd språk som C#, F # eller python.

## <a name="pre-requisites"></a>Förutsättningar

- [.NET Core SDK 3,1 eller senare](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Även om du kan bygga Q #-kommando rads program i vilken IDE som helst, rekommenderar vi starkt att du använder Visual Studio Code (VS Code) eller Visual Studio IDE för dina Q #-program. Genom att använda VS Code eller Visual Studio och QDK Visual Studio Code-tillägget får du till gång till mer avancerade funktioner.

- Installera [vs Code](https://code.visualstudio.com/download) (Windows, Linux och Mac)
- Installera [QDK-tillägget för vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) eller
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat
- Ladda ned och installera [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Utveckla med Q # med VS Code

Installera Quantum-projektmallarna:

- Gå till **Visa** -> **kommando palett**
- Välj **Q #: installera projektmallar**

Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.
- Skapa ett nytt projekt:
  - Gå till **Visa** -> **kommando palett**
  - Välj **Q #: skapa nytt projekt**
  - Välj **fristående konsol program**
  - Gå till den plats i filsystemet där du vill skapa programmet
  - Klicka på knappen **Öppna nytt projekt...** när projektet har skapats
        
- Inspektera projektet
  - Du bör se att en fil som `Program.qs` heter skapad, som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.

- Kör programmet:
  - Gå till **Terminal** -> ,**ny terminal**
  - Ange `dotnet run`
  - Du bör se följande text i utdatafönstret `Hello quantum world!`


> [!NOTE]
> * Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

## <a name="develop-with-q-using-visual-studio"></a>Utveckla med Q # med Visual Studio

Verifiera installationen genom att skapa ett `Hello World`-program

- Skapa ett nytt Q#-program
  - Gå till **filen** -> **nytt** -> **projekt**
  - Skriv `Q#` i sökrutan
  - Välj **Q#-program**
  - Välj **Nästa**
  - Välj ett namn och en plats för ditt program
  - Välj **skapa**

- Inspektera projektet
  - Du bör se att en fil som `Program.qs` heter har skapats, som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.

- Köra appen
  - Välj **fel söknings** -> **Start utan fel sökning**
  - Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.

> [!NOTE]
> * Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.  


## <a name="whats-next"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).
