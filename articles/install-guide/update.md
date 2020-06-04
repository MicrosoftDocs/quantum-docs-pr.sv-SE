---
title: Uppdatera Quantum Development Kit (QDK)
description: 'Beskriver hur du uppdaterar dina Q #-projekt och Microsoft Quantum Development Kit till den aktuella versionen.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327584"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Uppdatera Microsoft Quantum Development Kit (QDK)

Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.

Den här artikeln förutsätter att du redan har installerat QDK. Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.

Vi rekommenderar att du håller dig uppdaterad med den senaste versionen av QDK. Följ den här uppdaterings guiden för att uppgradera till den senaste versionen av QDK. Processen består av två delar:
1. Uppdatera dina befintliga Q #-filer och-projekt för att justera koden med en uppdaterad syntax.
2. Uppdatera själva QDK för din valda utvecklings miljö.

## <a name="updating-q-projects"></a>Uppdaterar Q # projekt 

Följ dessa anvisningar om du vill uppdatera dina Q #-projekt oavsett om du använder C# eller python som värd för Q #-åtgärder.

1. Kontrol lera först att du har den senaste versionen av [.NET Core SDK 3,1](https://dotnet.microsoft.com/download). Kör följande kommando i kommando tolken:

    ```dotnetcli
    dotnet --version
    ```

    Kontrol lera att utdata är `3.1.100` eller högre. Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen. Följ sedan anvisningarna nedan beroende på dina inställningar (Visual Studio, Visual Studio Code eller direkt på kommando raden).

### <a name="update-q-projects-in-visual-studio"></a>Uppdatera Q #-projekt i Visual Studio
 
1. Uppdatera till den senaste versionen av Visual Studio 2019, finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner.
2. Öppna din lösning i Visual Studio.
3. Välj **Bygg**  ->  **ren lösning**på menyn.
4. I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteks projekt).
    Det vill säga Redigera rader i formuläret:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. I var och en av CSPROJ-filerna ställer du in SDK till `Microsoft.Quantum.Sdk` , som anges i raden nedan. Observera att versions numret måste vara det senaste tillgängliga och du kan fastställa det genom att granska [versions anteckningarna](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Spara och Stäng alla filer i lösningen.

7. Välj **verktyg**  ->  **kommando rad**  ->  **utvecklare kommando tolk**. Du kan också använda paket hanterings konsolen i Visual Studio.

8. För varje projekt i lösningen kör du följande kommando för att **ta bort** det här paketet:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Om dina projekt använder andra Microsoft. Quantum-eller Microsoft. Azure. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot **Add** för att uppdatera den version som används.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Stäng kommando tolken och välj **skapa**  ->  **build-lösning** (Välj *inte* att återskapa lösningen).

Nu kan du gå vidare till [Uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Uppdatera Q #-projekt i Visual Studio Code

1. Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code.
2. Välj **Terminal**-  ->  **ny terminal**.
3. Följ anvisningarna för uppdatering med hjälp av kommando raden (direkt nedan).

### <a name="update-q-projects-using-the-command-line"></a>Uppdatera Q #-projekt med hjälp av kommando raden

1. Navigera till mappen som innehåller huvud projekt filen.

2. Kör följande kommando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Bestäm den aktuella versionen av QDK. För att hitta det kan du läsa [viktig information](https://docs.microsoft.com/quantum/relnotes/). Versionen är i ett format som liknar `0.11.2006.207` .

4. I var och en av dina `.csproj` filer går du igenom följande steg:

    - Uppdatera mål ramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteks projekt). Det vill säga Redigera rader i formuläret:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Ersätt referensen till SDK i projekt definitionen. Kontrol lera att versions numret motsvarar det värde som fastställs i **steg 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Ta bort referensen till paketet `Microsoft.Quantum.Development.Kit` , om den finns, som ska anges i följande post:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Uppdatera versionen av alla Microsoft Quantum-paket till den senast utgivna versionen av QDK (som fastställs i **steg 3**). Dessa paket namnges med följande mönster:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Referenser till paket har följande format:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Spara den uppdaterade filen.

    - Återställ projektets beroenden genom att göra följande:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Navigera tillbaka till mappen som innehåller huvud projektet och kör:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

När du har uppdaterat dina Q #-projekt följer du anvisningarna nedan för att uppdatera själva QDK.

## <a name="updating-the-qdk"></a>Uppdaterar QDK

Processen för att uppdatera QDK varierar beroende på ditt utvecklings språk och miljö.
Välj din utvecklings miljö nedan.

* [Python: uppdatera SWEETIQ #-tillägget](#update-iq-for-python)
* [Jupyter Notebook: uppdatera SWEETIQ #-tillägget](#update-iq-for-jupyter-notebooks)
* [Visual Studio: uppdatera tillägget QDK](#update-visual-studio-qdk-extension)
* [VS Code: uppdatera tillägget QDK](#update-vs-code-qdk-extension)
* [Kommando rad och C#: uppdatera projektmallar](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Uppdatera SWEETIQ # för python

1. Uppdatera `iqsharp` kerneln 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifiera `iqsharp` versionen

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Du bör se följande utdata:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Oroa dig inte om din `iqsharp` version är högre, den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).

3. Uppdatera `qsharp` paketet

    ```bash
    pip install qsharp --upgrade
    ```

4. Verifiera `qsharp` versionen

    ```bash
    pip show qsharp
    ```

    Du bör se följande utdata:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Kör följande kommando från platsen för dina `.qs` filer

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.

### <a name="update-iq-for-jupyter-notebooks"></a>Uppdatera SWEETIQ # för Jupyter-anteckningsböcker

1. Uppdatera `iqsharp` kerneln

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifiera `iqsharp` versionen

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Dina utdata bör likna följande:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Oroa dig inte om din `iqsharp` version är högre, den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).

3. Kör följande kommando från en cell i Jupyter Notebook:

    ```
    %workspace reload
    ```

4. Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.

### <a name="update-visual-studio-qdk-extension"></a>Uppdatera Visual Studio QDK-tillägg

1. Uppdatera Q # Visual Studio-tillägget

    - Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Godkänn uppdateringen

    > [!NOTE]
    > Projektfilerna uppdateras med tillägget. De uppdaterade mallarna gäller endast för nyligen skapade projekt. Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.

### <a name="update-vs-code-qdk-extension"></a>Uppdatera VS Code QDK-tillägg

1. Uppdatera tillägget för Quantum VS Code

    - Starta om VS-kod
    - Navigera till fliken **tillägg**
    - Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg
    - Läs in tillägget igen

2. Uppdatera Quantum-projektmallar:

   - Gå till **Visa**  ->  **kommando palett**
   - Välj **Q #: installera projektmallar**
   - Efter några sekunder bör du få ett popup-meddelande om att Project-mallar har installerats

### <a name="c-using-the-dotnet-command-line-tool"></a>C# med `dotnet` kommando rads verktyget

1. Uppdatera Quantum Project-mallar för .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
