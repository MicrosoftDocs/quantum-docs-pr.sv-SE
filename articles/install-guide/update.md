---
title: Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463278"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Uppdatera Microsoft Quantum Development Kit (QDK)

Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.

Den här artikeln förutsätter att du redan har installerat QDK. Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.


## <a name="updating-q-projects"></a>Uppdaterar Q # projekt 

1. Installera först den senaste versionen av [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) och kör följande kommando i kommando tolken:
```bash
dotnet --version
```
 Kontrol lera att utdata är 3.0.100 eller högre, och följ anvisningarna nedan beroende på dina inställningar.

### <a name="in-visual-studio"></a>I Visual Studio 2013
 
 1. Uppdatera till den senaste versionen av Visual Studio 2019 finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner
 2. Öppna din lösning i Visual Studio
 3. På menyn väljer du build > ren lösning 
 4. [Uppdatera mål ramverket](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) i var och en av dina. CSPROJ-filer till netcoreapp 3.0 (eller netstandard 2.1 om det är ett biblioteks projekt)
 5. Spara och Stäng alla filer i lösningen
 6. Välj Verktyg > kommando rad > Developer kommando tolken
 7. Kör följande kommando för varje projekt i lösningen:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Om dina projekt använder andra Microsoft. Quantum-paket kör du kommandot för dessa. 
 8. Stäng kommando tolken och välj build > build-lösning (Välj *inte* att återskapa lösningen, eftersom återställningen kommer att Miss Förslut ATS)

### <a name="in-visual-studio-code"></a>I Visual Studio Code

1. Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code
1. Välj Terminal > ny terminal
1. Följ anvisningarna för att uppdatera med hjälp av kommando raden

### <a name="using-the-command-line"></a>Använda kommando raden

1. Navigera till mappen som innehåller projekt filen
2. Kör följande kommando:
```bash
dotnet clean [project_name].csproj
```

3. [Uppdatera mål ramverket](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) i var och en av dina. CSPROJ-filer till netcoreapp 3.0 (eller netstandard 2.1 om det är ett biblioteks projekt)
4. Kör följande kommando:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
om projektet använder andra Microsoft. Quantum-paket kör du kommandot för dessa.

5. Spara och Stäng alla filer
6. Upprepa 1-4 för varje projekt beroende och gå sedan tillbaka till mappen som innehåller huvud projektet och kör:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Uppdatera SWEETIQ # för python

1. Uppdatera `iqsharp` kernel

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verifiera `iqsharp` versionen

    ```bash
    dotnet iqsharp --version
    ```

    Du bör se följande utdata:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. Uppdatera `qsharp`-paketet

    ```bash
    pip install qsharp --upgrade
    ```

1. Verifiera `qsharp` versionen

    ```bash
    pip show qsharp
    ```

    Du bör se följande utdata:

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Kör följande kommando från platsen för dina `.qs`-filer
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.

## <a name="update-iq-for-jupyter-notebooks"></a>Uppdatera SWEETIQ # för Jupyter-anteckningsböcker

1. Uppdatera `iqsharp` kernel

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verifiera `iqsharp` versionen

    ```bash
    dotnet iqsharp --version
    ```

    Du bör se följande utdata:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Kör följande kommando från en cell i Jupyter Notebook:
    ```
    %workspace reload
    ```

1. Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.

## <a name="update-visual-studio-qdk-extension"></a>Uppdatera Visual Studio QDK-tillägg

1. Uppdatera Q # Visual Studio-tillägget

    - Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Godkänn uppdateringen

    > [!NOTE]
    > Projektfilerna uppdateras med tillägget. De uppdaterade mallarna gäller endast för nyligen skapade projekt. Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.

## <a name="update-vs-code-qdk-extension"></a>Uppdatera VS Code QDK-tillägg

1. Uppdatera tillägget för Quantum VS Code

    - Starta om VS-kod
    - Navigera till fliken **tillägg**
    - Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg
    - Läs in tillägget igen

1. Uppdatera Quantum-projektmallar:

   - Gå till **Visa** -> **Kommandopaletten**
   - Välj **Q #: installera projektmallar**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, med hjälp av kommando rads verktyget `dotnet`

1. Uppdatera Quantum Project-mallar för .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Vad står på tur?

Nu när du har uppdaterat Quantum Development Kit i din önskade miljö kan du fortsätta att utveckla och köra dina Quantum-program. Om du inte har skrivit ett program ännu kan du komma igång med [ditt första Quantum-program](xref:microsoft.quantum.write-program).
