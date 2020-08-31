---
title: Uppdatera Quantum Development Kit (QDK)
description: Beskriver hur du uppdaterar Q#-projekt och Microsoft Quantum Development Kit till den aktuella versionen.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 84782d1628dd100c0939b2b12aa0a9aa8ab2b80e
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863646"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Uppdatera Microsoft Quantum Development Kit (QDK)

Lär dig att uppdatera Microsoft Quantum Development Kit till den senaste versionen.

Den här artikeln förutsätter att du redan har installerat QDK. Om du installerar för första gången kan du läsa [installationsguiden](xref:microsoft.quantum.install).

Vi rekommenderar att har den senaste QDK-versionen. Följ den här uppdateringsguiden för att uppgradera till den senaste QDK-versionen. Processen består av två delar:
1. Uppdatera dina befintliga Q#-filer och projekt för att justera koden med en uppdaterad syntax.
2. Uppdatera själva QDK:n för din valda utvecklingsmiljö.

## <a name="updating-no-locq-projects"></a>Uppdatera Q#-projekt 

Oavsett om du använder C# eller Python för att värdhantera Q#-åtgärder följer du dessa instruktioner för att uppdatera dina Q#-projekt.

1. Kontrollera först att du har den senaste versionen av [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Kör följande kommando i kommandotolken:

    ```dotnetcli
    dotnet --version
    ```

    Kontrollera att utdatan är `3.1.100` eller högre. Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen. Följ sedan anvisningarna nedan beroende på din konfiguration (Visual Studio, Visual Studio Code eller direkt från kommandotolken).

### <a name="update-no-locq-projects-in-visual-studio"></a>Uppdatera Q#-projekt i Visual Studio
 
1. Uppdatera till den senaste versionen av Visual Studio 2019. Mer information finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).
2. Öppna därefter lösningen i Visual Studio.
3. I menyn väljer du **Version** -> **Rensa lösning**.
4. I varje .csproj-fil uppdaterar du målramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteksprojekt).
    Det innebär att redigera rader i formuläret:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Mer information om att ange målramverk finns [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. I var och en av .csproj-filerna ställer du in SDK:n på `Microsoft.Quantum.Sdk`, enligt raden nedan. Observera att versionsnumret måste vara det senaste tillgängliga. Du hittar det i [Viktig information](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. Spara och stäng alla filer i lösningen.

7. Välj **Verktyg** -> **Kommandorad** -> **Kommandotolk för utvecklare**. Du kan också använda pakethanteringskonsolen i Visual Studio.

8. Kör följande kommando för att **ta bort** paketet från alla projekt i lösningen:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Om dina projekt använder andra Microsoft.Quantum- eller Microsoft.Azure.Quantum-paket (t.ex. Microsoft.Quantum.Numerics), kör du kommandot **Lägg till** för att uppdatera den version som används.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Stäng kommandotolken och välj **Version** -> **Skapa lösning** (välj *inte* Återskapa lösning).

Nu kan du gå vidare med att [uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).


### <a name="update-no-locq-projects-in-visual-studio-code"></a>Uppdatera Q#-projekt i Visual Studio Code

1. I Visual Studio Code öppnar du mappen med projektet som ska uppdateras.
2. Välj **Terminal** -> **Ny terminal**.
3. Följ anvisningarna för uppdatering med kommandotolken (visas nedan).

### <a name="update-no-locq-projects-using-the-command-prompt"></a>Uppdatera Q#-projekt med kommandotolken

1. Gå till mappen med huvudprojektfilen.

2. Kör följande kommando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Fastställ den aktuella QDK-versionen. För att hitta den kan du läsa [Viktig information](https://docs.microsoft.com/quantum/relnotes/). Versionen är i ett format som liknar `0.12.20072031`.

4. Gå igenom följande steg för alla dina `.csproj`-filer:

    - Uppdatera målramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteksprojekt). Det innebär att redigera rader i formuläret:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Mer information om att ange målramverk finns [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Ersätt referensen till SDK:n i projektdefinitionen. Kontrollera att versionsnumret motsvarar det värde som fastställdes i **steg 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - Ta bort referensen till paket `Microsoft.Quantum.Development.Kit`, om ett sådant finns, vilket anges i följande post:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Uppdatera versionen av alla Microsoft Quantum-paket till den senast utgivna versionen av QDK:n (fastställs i **steg 3**). Dessa paket namnges enligt följande mönster:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Referenser till paket har följande format:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - Spara den uppdaterade filen.

    - Återställ projektets beroenden genom att göra följande:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Gå tillbaka till mappen med huvudprojektet och kör:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Nu när du har uppdaterat dina Q#-projekt följer du anvisningarna nedan för att uppdatera själva QDK:n.

## <a name="updating-the-qdk"></a>Uppdaterar QDK:n

Processen för att uppdatera QDK:n varierar beroende på utvecklingsspråk och miljö.
Välj din utvecklingsmiljö nedan.

* [Python: uppdatera `qsharp`-paketet](#update-the-qsharp-python-package)
* [Jupyter Notebooks: uppdatera IQ#-kärnan](#update-the-iq-jupyter-kernel)
* [Visual Studio: Uppdatera QDK-tillägget](#update-visual-studio-qdk-extension)
* [VS Code: Uppdatera QDK-tillägget](#update-vs-code-qdk-extension)
* [Kommandorad och C#: Uppdatera projektmallar](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>Uppdatera Python-paketet `qsharp`

Uppdateringsproceduren beror på om du ursprungligen installerade med hjälp av conda eller med .NET CLI och pip.

#### <a name="update-using-conda-recommended"></a>[Uppdatera med hjälp av conda (rekommenderas)](#tab/tabid-conda)

1. Aktivera den conda-miljö där du installerade `qsharp`-paketet och kör sedan det här kommandot för att uppdatera det:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Kör följande kommando från platsen för dina `.qs`-filer:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Uppdatera med hjälp av .NET CLI och pip (avancerat)](#tab/tabid-dotnetcli)

1. Uppdatera din `iqsharp`-kernel 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Kontrollera `iqsharp`-versionen

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Du bör se följande utdata:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Oroa dig inte om din `iqsharp`-version är högre. Den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).

1. Uppdatera `qsharp`-paketet:

    ```
    pip install qsharp --upgrade
    ```

1. Kontrollera `qsharp`-versionen:

    ```
    pip show qsharp
    ```

    Du bör se följande utdata:

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Kör följande kommando från platsen för dina `.qs`-filer:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

Nu kan du använda det uppdaterade Python-paketet `qsharp` till att köra befintliga kvantprogram.

### <a name="update-the-ino-locq-jupyter-kernel"></a>Uppdatera IQ# Jupyter-kärnan

Uppdateringsproceduren beror på om du ursprungligen installerade med hjälp av conda eller med .NET CLI och pip.

#### <a name="update-using-conda-recommended"></a>[Uppdatera med hjälp av conda (rekommenderas)](#tab/tabid-conda)

1. Aktivera den conda-miljö där du installerade `qsharp`-paketet och kör sedan det här kommandot för att uppdatera det:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Kör följande kommando från en cell i var och en av dina befintliga Q#-Jupyter Notebooks:

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Uppdatera med hjälp av .NET CLI och pip (avancerat)](#tab/tabid-dotnetcli)

1. Uppdatera `Microsoft.Quantum.IQSharp`-paketet:

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Kontrollera `iqsharp`-versionen:

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Ditt resultat bör likna följande:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Oroa dig inte om din `iqsharp`-version är högre. Den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).

1. Kör följande kommando från en cell i var och en av dina befintliga Q#-Jupyter Notebooks:

    ```
    %workspace reload
    ```

***

Nu kan du använda den uppdaterade IQ#-kärnan för att köra dina befintliga Q#-Jupyter Notebooks.

### <a name="update-visual-studio-qdk-extension"></a>Uppdatera QDK-tillägg i Visual Studio

1. Uppdatera Visual Studio-tillägget för Q#

    - Visual Studio uppmanar dig att acceptera uppdateringar av [Quantum-tillägget för Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Godkänn uppdateringen

    > [!NOTE]
    > Projektmallarna uppdateras med tillägget. De uppdaterade mallarna gäller endast för nyligen skapade projekt. Koden i dina befintliga projekt uppdateras inte när tillägget uppdateras.

### <a name="update-vs-code-qdk-extension"></a>Uppdatera QDK-tillägg för VS Code

1. Uppdatera Quantum-tillägget för VS Code

    - Starta om VS Code
    - Gå till fliken **Tillägg**
    - Välj tillägget **Microsoft Quantum Development Kit för Visual Studio Code**
    - Läs in tillägget på nytt

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, med hjälp av kommandoradsverktyget `dotnet`

1. Uppdatera Quantum-projektmallar för .NET

    I kommandotolken:

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   Om du tänker använda kommandoradsmallarna och redan har installerat QDK-tillägget för VS Code kan du också uppdatera projektmallarna från själva tillägget:

   - [Uppdatera QDK-tillägget](#update-vs-code-qdk-extension)
   - Gå till **Visa** -> **Kommandopaletten** i VS Code
   - Välj **Q#: Installera projektmallar från kommandoraden**
   - Efter några sekunder bör du få ett popup-meddelande som bekräftar att ”projektmallar har installerats”
