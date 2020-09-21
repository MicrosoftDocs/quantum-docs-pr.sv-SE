---
title: Utveckla med Q# och .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 96a1d0d75f3ff7de11407fd76479cbae86ce7571
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759280"
---
# <a name="develop-with-no-locq-and-net"></a>Utveckla med Q# och .NET

Q# är utformat att fungera med .NET-språk som C# och F# .
I den här guiden visar vi hur du använder Q# med ett värdprogram som skrivits i ett .NET-språk.

Först skapar vi Q#-programmet och .NET-värden, och sedan visar vi hur du anropar Q# från värden.

## <a name="prerequisites"></a>Krav

- Installera Quantum Development Kit [för användning med projekt i Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-no-locq-library-and-a-net-host"></a>Skapa ett Q#-bibliotek och en .NET-värd

Det första steget är att skapa projekt för ditt Q#-bibliotek och för den .NET-värd som ska anropa åtgärder och funktioner som definierats i ditt Q#-bibliotek.

Följ anvisningarna på den flik som motsvarar din utvecklingsmiljö.
Om du använder ett annat redigeringsprogram än Visual Studio eller VS Code följer du bara stegen för kommandotolken.

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code eller kommandotolk](#tab/tabid-cmdline)

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

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Skapa ett nytt Q#-bibliotek
  - Gå till **Arkiv** -> **Nytt** -> **Projekt**
  - Skriv "Q#" i sökrutan
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

***

## <a name="calling-into-no-locq-from-net"></a>Anropa till Q# från .NET

När du har konfigurerat dina projekt enligt anvisningarna ovan, kan du anropa Q# från ditt .NET-konsolprogram.
Q#-kompileraren skapar .NET-klasser för varje Q#-åtgärd och funktion, så att du kan köra kvantprogrammen i en simulator.

[I exemplet på .NET-interoperabilitet](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) finns följande exempel på en Q#-åtgärd:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Om du vill anropa den här åtgärden från .NET i en kvantsimulator, kan du använda `Run`-metoden för den `RunAlgorithm`-.NET-klass som genererades av Q#-kompileraren:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Nästa steg

Nu när du har konfigurerat Quantum Development Kit för både Q#-program och interoperabilitet med .NET kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
