---
title: 'Utveckla med Q # kommando rads program'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426426"
---
# <a name="develop-with-q-command-line-applications"></a>Utveckla med Q # kommando rads program

Q #-program kan köras på egen hand utan en driv rutin på ett värd språk som C#, F # eller python.

## <a name="pre-requisites"></a>Förutsättningar

- [.NET Core SDK 3,1 eller senare](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installation

Även om du kan bygga Q #-kommando rads program i vilken IDE som helst, rekommenderar vi att du använder Visual Studio Code (VS Code) eller Visual Studio IDE för dina Q #-program. Att utveckla i dessa verktyg ger till gång till omfattande funktioner.

Så här konfigurerar du VS-kod:

1. Ladda ned och installera [vs Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).
2. Installera [Microsoft QDK for vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Så här konfigurerar du Visual Studio:

1. Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 eller senare med arbets belastningen .net Core plattforms oberoende utveckling aktive rad.
2. Hämta och installera [Microsoft-QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Utveckla med Q # med VS Code

Installera mallarna för Q #-projekt:

1. Öppen VS Code.
2. Klicka på **Visa**  ->  **kommando palett**.
3. Välj **Q #: installera projektmallar**.

När **projektmallar har installerats** visas QDK som är redo att användas med dina egna program och bibliotek.

Så här skapar du ett nytt projekt:

1. Klicka på **Visa**  ->  **kommando palett** och välj **Q #: skapa nytt projekt**.
2. Klicka på **fristående konsol program**.
3. Navigera till platsen där du vill spara projektet och klicka på **skapa projekt**.
4. När projektet har skapats klickar du på **Öppna nytt projekt...** i det nedre högra hörnet.
        
Inspektera projektet. Du bör se en käll fil med namnet `Program.qs` , som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.

Så här kör du programmet:
1. Klicka på **Terminal**-  ->  **ny terminal**.
2. Skriv i Terminal-prompten `dotnet run` .
3. Du bör se följande text i utdatafönstret `Hello quantum world!`


> [!NOTE]
> Arbets ytor med flera rotmappar stöds för närvarande inte av tillägget VS Code #. Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.

## <a name="develop-with-q-using-visual-studio"></a>Utveckla med Q # med Visual Studio

Verifiera din Visual Studio-installation genom att skapa ett Q #- `Hello World` program.

Så här skapar du ett nytt Q #-program:
1. Öppna Visual Studio och klicka på **fil**  ->  **nytt**  ->  **projekt**.
2. Skriv `Q#` i sökrutan, Välj **Q #-program** och klicka på **Nästa**.
3. Ange ett namn och en plats för ditt program och klicka på **skapa**.


Inspektera projektet. Du bör se en käll fil med namnet `Program.qs` , som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.

Så här kör du programmet:
1. Välj **fel söknings**  ->  **Start utan fel sökning**.
2. Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.

> [!NOTE]
> Om du har flera projekt i en Visual Studio-lösning måste alla projekt som finns i lösningen finnas i samma mapp som lösningen eller i en av dess undermappar.  


## <a name="next-steps"></a>Nästa steg

Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
