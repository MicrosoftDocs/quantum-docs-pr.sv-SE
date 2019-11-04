---
title: Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185859"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Uppdatera Microsoft Quantum Development Kit (QDK)

Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.

Den här artikeln förutsätter att du redan har installerat QDK. Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.

Uppdaterings stegen är beroende av utvecklings miljön. Välj din miljö i följande avsnitt.

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.

## <a name="jupyter-notebooks"></a>Jupyter Notebooks

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.

## <a name="c-on-windows-using-visual-studio"></a>C#i Windows använder du Visual Studio

1. Uppdatera Q # Visual Studio-tillägget

    - Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Godkänn uppdateringen

    > [!NOTE]
    > Projektfilerna uppdateras med tillägget. De uppdaterade mallarna gäller endast för nyligen skapade projekt. Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.

1. Uppdatera QDK-paketen

    - Öppna ett befintligt program
    - Välj **beroenden** i Solution Explorer
    - Välj **Hantera NuGet-paket**
    - Uppdatera **Microsoft. Quantum** -paketen till den senaste versionen

1. Nu kan du köra ditt program med de senaste QDK.

## <a name="c-using-vs-code"></a>C#, med VS Code

1. Uppdatera tillägget för Quantum VS Code

    - Starta om VS-kod
    - Navigera till fliken **tillägg**
    - Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg
    - Läs in tillägget igen

1. Uppdatera Quantum-projektmallar:

   - Gå till **visa** -> **kommando paletten**
   - Välj **Q #: installera projektmallar**

1. Öppna ett befintligt program i VS Code

   - Redigera. CSPROJ-filen för att lägga till nya paket versioner

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Om du använder andra `Microsoft.Quantum`-paket uppdaterar du dem också.

1. Nu kan du köra ditt program med den uppdaterade QDK

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, med hjälp av kommando rads verktyget `dotnet`

1. Uppdatera Quantum Project-mallar för .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Uppdatera och köra ett befintligt program

    - Uppdatera QDK-paket versionerna i ditt program

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Om programmet använder andra `Microsoft.Quantum`-paket uppdaterar du dem också.

    - Köra programmet

        ```bash
        dotnet run
        ```

    - Programmet kommer att köras med de nya paket versionerna

## <a name="whats-next"></a>Vad står på tur?

Nu när du har uppdaterat Quantum Development Kit i din önskade miljö kan du fortsätta att utveckla och köra dina Quantum-program. Om du inte har skrivit ett program ännu kan du komma igång med [ditt första Quantum-program](xref:microsoft.quantum.write-program).
