---
title: Utveckla med Q# och .NET
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426493"
---
# <a name="develop-with-q-and-net"></a>Utveckla med Q# och .NET

Q # är utformat för att spelas upp bra med .NET-språk som C# och F #.
I den här guiden visar vi hur du använder Q # med ett värd program skrivet på ett .NET-språk.

## <a name="prerequisites"></a>Krav

- Installera Quantum Development Kit [för användning med kommando rads projekt i Q #](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Skapa ett Q #-bibliotek och en .NET-värd

Det första steget är att skapa projekt för ditt Q #-bibliotek och för den .NET-värd som ska anropa de åtgärder och funktioner som definierats i ditt Q #-bibliotek.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Skapa ett nytt Q #-bibliotek
  - Gå till **filen**  ->  **nytt**  ->  **projekt**
  - Skriv "Q #" i sökrutan
  - Välj **Q #-bibliotek**
  - Välj **Nästa**
  - Välj ett namn och en plats för ditt bibliotek
  - Se till att "placera projektet och lösningen i samma katalog" är **avmarkerat**
  - Välj **skapa**
- Skapa ett nytt C#-eller F #-värd program
  - Gå till **Arkiv** → **nytt** → **projekt**
  - Välj "konsol program (.NET Core") "för antingen C# eller F #
  - Välj **Nästa**
  - Under *lösning*väljer du "Lägg till i lösning"
  - Välj ett namn för värd programmet
  - Välj **skapa**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio-kod eller kommando rad](#tab/tabid-cmdline)

- Skapa ett nytt Q #-bibliotek

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Skapa ett nytt C#-eller F #-konsol projekt

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Lägg till ditt Q #-bibliotek som en referens från värd programmet

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Valfritt Skapa en lösning för båda projekten

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Anrop till Q # från .NET

När du har skapat dina projekt enligt anvisningarna ovan kan du anropa i Q # från ditt .NET-konsol program.
I Q #-kompilatorn skapas .NET-klasser för varje Q #-åtgärd och-funktion som gör att du kan köra dina Quantum-program på en simulator.

Exempel på .net- [interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) innehåller följande exempel på en Q #-åtgärd:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Om du vill anropa den här åtgärden från .NET på en Quantum-simulator kan du använda `Run` metoden för `RunAlgorithm` .net-klassen som genereras av Q #-kompilatorn:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Nästa steg

Nu när du har Quantum Development Kit konfigurerat för både Q # kommando rads program och för interoperabilitet med .NET, kan du skriva och köra [ditt första Quantum-program](xref:microsoft.quantum.quickstarts.qrng).
