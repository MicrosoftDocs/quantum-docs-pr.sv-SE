---
title: Utveckla med Q# och .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274156"
---
# <a name="develop-with-q-and-net"></a>Utveckla med Q# och .NET

Q# är utformat att fungera med .NET-språk som C# och F# .
I den här guiden visar vi hur du använder Q# med ett värdprogram skrivet med ett .NET-språk.

## <a name="prerequisites"></a>Krav

- Installera Quantum Development Kit [för användning med kommandoradsprojekt i Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Skapa ett Q#-bibliotek och en .NET-värd

Det första steget är att skapa projekt för ditt Q#-bibliotek och för den .NET-värd som ska anropa åtgärder och funktioner som definierats i ditt Q#-bibliotek.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Skapa ett nytt Q#-bibliotek
  - Gå till **Arkiv** -> **Nytt** -> **Projekt**
  - Skriv ”Q#” i sökrutan
  - Välj **Q#-bibliotek**
  - Välj **Nästa**
  - Välj ett namn och en plats för ditt bibliotek
  - Kontrollera att ”Placera projektet och lösningen i samma katalog” är **avmarkerat**
  - Välj **Skapa**
- Skapa ett nytt C#- eller F#-värdprogram
  - Gå till **Arkiv** → **Nytt** → **Projekt**
  - Välj ”Konsolapp (.NET Core”)” för antingen C# eller F#
  - Välj **Nästa**
  - Under *Lösning*väljer du ”Lägg till i lösning”
  - Välj ett namn på värdprogrammet
  - Välj **Skapa**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code eller kommandorad](#tab/tabid-cmdline)

- Skapa ett nytt Q#-bibliotek

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Skapa ett nytt C#- eller F#-konsolprojekt

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Lägg till ditt Q#-bibliotek som en referens från värdprogrammet

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Valfritt] Skapa en lösning för båda projekten

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Anropa Q# från .NET

När du har konfigurerat dina projekt enligt anvisningarna ovan, kan du anropa Q# från ditt .NET-konsolprogram.
Q#-kompileraren skapar .NET-klasser för varje Q#-åtgärd och funktion, så att du kan köra kvantprogrammen i en simulator.

[I exemplet på .NET-interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) visas följande Q#-åtgärd:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Om du vill anropa den här åtgärden från .NET i en kvantsimulator, kan du använda `Run`-metoden för den `RunAlgorithm`-.NET-klass som genererades av Q#-kompileraren:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Nästa steg

Nu när du har konfigurerat Quantum Development Kit för både Q#-kommandoradsprogram och för interoperabilitet med .NET, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
