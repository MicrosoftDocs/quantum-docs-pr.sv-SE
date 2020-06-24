---
title: 'Installation och verifiering av Microsoft Q # kemi Library'
description: Lär dig hur du installerar Microsoft Quantum kemi-biblioteket och använder det med NWChem-plattformen för beräknings kemi.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276099"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="33b6d-103">Installation och verifiering av kemi-bibliotek</span><span class="sxs-lookup"><span data-stu-id="33b6d-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="33b6d-104">Quantum Development Kit har stöd för Quantum kemi-program via [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet-paketet.</span><span class="sxs-lookup"><span data-stu-id="33b6d-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="33b6d-105">Precis som med andra NuGet-paket är det enkelt att lägga till kemi-biblioteket i projektet.</span><span class="sxs-lookup"><span data-stu-id="33b6d-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="33b6d-106">**Visual Studio 2019:** Om du använder Visual Studio 2019 kan du lägga till Quantum kemi-paketen med hjälp av NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="33b6d-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="33b6d-107">Om du vill öppna paket hanteraren högerklickar du på det projekt som du vill lägga till kemi-biblioteket i och väljer "hantera NuGet-paket..." som i skärm bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="33b6d-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![Använda NuGet Package Manager i Visual Studio 2019](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="33b6d-109">Sök efter paket namnet "Microsoft. Quantum. kemi" från fliken Bläddra.</span><span class="sxs-lookup"><span data-stu-id="33b6d-109">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="33b6d-110">Se till att kryssa för "inkludera för hands version".</span><span class="sxs-lookup"><span data-stu-id="33b6d-110">Make sure to tick "Include prerelease."</span></span>

![Kryss rutan inkludera för hands version](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="33b6d-112">Detta visar de paket som är tillgängliga för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="33b6d-112">This will list the packages available for download.</span></span>
<span data-ttu-id="33b6d-113">Klicka på Microsoft. Quantum. kemi i den vänstra rutan, Välj den senaste för hands versionen i rutan till höger och klicka på "installera":</span><span class="sxs-lookup"><span data-stu-id="33b6d-113">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![Installera det senaste Microsoft. Quantum. kemi-paketet](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="33b6d-115">Mer information finns i UI- [guiden för paket hanteraren](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="33b6d-115">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="33b6d-116">Du kan också använda Package Manager-konsolen för att lägga till Quantum kemi-biblioteket i projektet med ett kommando rads gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="33b6d-116">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![Använda Package Manager-konsolen från kommando raden](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="33b6d-118">Kör följande från Package Manager-konsolen:</span><span class="sxs-lookup"><span data-stu-id="33b6d-118">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="33b6d-119">Mer information finns i Guide till [Package Manager-konsolen](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="33b6d-119">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="33b6d-120">**Kommando rad eller Visual Studio Code:** Med hjälp av kommando raden i sin egen eller från Visual Studio Code kan du använda `dotnet` kommandot för att lägga till NuGet-paket referens i projektet:</span><span class="sxs-lookup"><span data-stu-id="33b6d-120">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="33b6d-121">Verifiera installationen</span><span class="sxs-lookup"><span data-stu-id="33b6d-121">Verifying Your Installation</span></span> 

<span data-ttu-id="33b6d-122">Precis som resten av Quantum Development Kit, innehåller Quantum kemi-biblioteket ett antal fullständigt dokumenterade exempel som hjälper dig att komma igång snabbt.</span><span class="sxs-lookup"><span data-stu-id="33b6d-122">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="33b6d-123">Om du vill testa installationen med hjälp av dessa exempel kan du klona [huvud exempel lagrings platsen](https://github.com/Microsoft/Quantum)och sedan köra ett av exemplen.</span><span class="sxs-lookup"><span data-stu-id="33b6d-123">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="33b6d-124">För att till exempel köra [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) exemplet:</span><span class="sxs-lookup"><span data-stu-id="33b6d-124">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="33b6d-125">Verifiera installationen av Quantum kemi-biblioteket med hjälp av Microsoft Visual Studio efter kloning av lagrings platsen:</span><span class="sxs-lookup"><span data-stu-id="33b6d-125">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="33b6d-126">Öppna lösningen ChemistrySamples. SLN i kemi-mappen.</span><span class="sxs-lookup"><span data-stu-id="33b6d-126">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="33b6d-127">Välj exempel/1.</span><span class="sxs-lookup"><span data-stu-id="33b6d-127">Select Samples/1.</span></span> <span data-ttu-id="33b6d-128">Enkel molekyl/MolecularHydrogen som start projekt.</span><span class="sxs-lookup"><span data-stu-id="33b6d-128">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="33b6d-129">Tryck på F5 för att köra uppskattnings demonstrationen av den molekyliga väte-fasen.</span><span class="sxs-lookup"><span data-stu-id="33b6d-129">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="33b6d-130">Mer information om hur du uppskattar värdena för energi nivåer finns i avsnittet [Hämta uppskattningar av energi nivå](xref:microsoft.quantum.chemistry.examples.energyestimate) .</span><span class="sxs-lookup"><span data-stu-id="33b6d-130">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="33b6d-131">Använda Quantum Development Kit med NWChem</span><span class="sxs-lookup"><span data-stu-id="33b6d-131">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="33b6d-132">MolecularHydrogen-exemplet använder molekyliska indata som har kon figurer ATS manuellt.</span><span class="sxs-lookup"><span data-stu-id="33b6d-132">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="33b6d-133">Även om det här är bra för små exempel kräver Quantum kemi i skala Hamiltonians med miljon tals eller miljarder villkor.</span><span class="sxs-lookup"><span data-stu-id="33b6d-133">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="33b6d-134">Sådan Hamiltonians, som genereras av skalbara beräknings kemi paket, är för stora för att kunna importeras manuellt.</span><span class="sxs-lookup"><span data-stu-id="33b6d-134">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="33b6d-135">Quantum kemi-biblioteket för Quantum Development Kit är utformat för att fungera bra med data kemi-paket, främst i [**NWChem**](http://www.nwchem-sw.org/) -miljön för beräknings vetenskap som utvecklats av EMSL (Environment Molekyle Science Science) på Stilla havs-och Stilla havs området.</span><span class="sxs-lookup"><span data-stu-id="33b6d-135">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="33b6d-136">`Microsoft.Quantum.Chemistry`Paketet innehåller särskilt verktyg för att läsa in instanser av Quantum kemi-simulerings problem som representeras i [Broombridge-schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), vilket också stöds för export av de senaste versionerna av NWChem.</span><span class="sxs-lookup"><span data-stu-id="33b6d-136">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="33b6d-137">För att komma igång med NWChem tillsammans med Quantum Development Kit föreslår vi en av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="33b6d-137">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="33b6d-138">Kom igång med att använda befintliga Broombridge-filer som finns i exemplen på [IntegralData/yaml](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="33b6d-138">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="33b6d-139">Använd [EMSL Arrows Builder för Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) som är en webbaserad frontend-fil till NWChem, för att generera nya Broombridge-formaterade molekyl indatafiler.</span><span class="sxs-lookup"><span data-stu-id="33b6d-139">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="33b6d-140">Använd [Docker-avbildningen](https://hub.docker.com/r/nwchemorg/nwchem-qc/) som tillhandahålls av PNNL för att köra NWChem, eller</span><span class="sxs-lookup"><span data-stu-id="33b6d-140">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="33b6d-141">[Kompilera NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) för din plattform.</span><span class="sxs-lookup"><span data-stu-id="33b6d-141">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="33b6d-142">I [slut punkt till slut punkt med NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) finns mer information om hur du arbetar med NWChem till kemiska modeller för att analysera med Quantum-biblioteket i Quantum utvecklaman-paketet.</span><span class="sxs-lookup"><span data-stu-id="33b6d-142">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="33b6d-143">Komma igång med Broombridge-filer som ingår i exemplen</span><span class="sxs-lookup"><span data-stu-id="33b6d-143">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="33b6d-144">Mappen [IntegralData/yaml](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) i exempel databasen i Quantum Development Kit innehåller Broombridge-formaterade molekyl data filer.</span><span class="sxs-lookup"><span data-stu-id="33b6d-144">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="33b6d-145">Som ett enkelt exempel kan du använda exempel biblioteket kemi Library, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) för att läsa in Hamiltonian från en av Broombridge-filerna och utföra grind uppskattningar av Quantum simulering algorigthms:</span><span class="sxs-lookup"><span data-stu-id="33b6d-145">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="33b6d-146">Mer information om hur du matar in molekyler som representeras av Broombridge-schemat finns i [läsa in en Hamiltonian från en fil](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="33b6d-146">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="33b6d-147">Se [Erhåll resurs antal](xref:microsoft.quantum.chemistry.examples.resourcecounts) för mer information om resurs uppskattning.</span><span class="sxs-lookup"><span data-stu-id="33b6d-147">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="33b6d-148">Komma igång med EMSL Arrows Builder</span><span class="sxs-lookup"><span data-stu-id="33b6d-148">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="33b6d-149">EMSL-pilarna är ett verktyg som använder NWChem och kemiska beräknings databaser för att generera molekyl data.</span><span class="sxs-lookup"><span data-stu-id="33b6d-149">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="33b6d-150">Med [EMSL Arrows Builder för Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) kan du ange din modell med flera molekyl modell byggare och generera Broombridge-datafilen som ska användas av Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="33b6d-150">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="33b6d-151">På sidan EMSL klickar du på fliken ["instuctions"] och följer instruktionerna för ["enkla exempel"] för att skapa Broombridge-filer.</span><span class="sxs-lookup"><span data-stu-id="33b6d-151">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="33b6d-152">Försök sedan att köra [' GetGateCount '] för att se Quantum Resource-uppskattningarna för dessa molekyler.</span><span class="sxs-lookup"><span data-stu-id="33b6d-152">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="33b6d-153">Installerar NWChem från källan</span><span class="sxs-lookup"><span data-stu-id="33b6d-153">Installing NWChem from Source</span></span>

<span data-ttu-id="33b6d-154">Fullständiga instruktioner för hur du installerar NWChem från källan finns [i PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="33b6d-154">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="33b6d-155">Om du vill använda NWChem från Windows 10 är Windows-undersystemet för Linux ett bra alternativ.</span><span class="sxs-lookup"><span data-stu-id="33b6d-155">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="33b6d-156">När du har installerat [Ubuntu 18,04-LTS för Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)kör du `ubuntu18.04` från din favorit Terminal och följer anvisningarna ovan för att installera NWChem från källan.</span><span class="sxs-lookup"><span data-stu-id="33b6d-156">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="33b6d-157">När du har kompilerat NWChem från källan kan du köra `yaml_driver` skriptet som medföljer NWChem för att snabbt producera Broombridge-instanser från NWChem-inmatade däck:</span><span class="sxs-lookup"><span data-stu-id="33b6d-157">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="33b6d-158">Med det här kommandot skapas en ny `input.yaml` fil i Broombridge-formatet i din aktuella katalog.</span><span class="sxs-lookup"><span data-stu-id="33b6d-158">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="33b6d-159">Använda NWChem med Docker</span><span class="sxs-lookup"><span data-stu-id="33b6d-159">Using NWChem with Docker</span></span>

<span data-ttu-id="33b6d-160">Färdiga avbildningar för att använda NWChem är tillgängliga mellan plattformar via [Docker Hub](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="33b6d-160">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="33b6d-161">Kom igång genom att följa Docker-installations anvisningarna för din plattform:</span><span class="sxs-lookup"><span data-stu-id="33b6d-161">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="33b6d-162">Installera Docker för Ubuntu</span><span class="sxs-lookup"><span data-stu-id="33b6d-162">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="33b6d-163">Installera Docker för macOS</span><span class="sxs-lookup"><span data-stu-id="33b6d-163">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="33b6d-164">Installera Docker för Windows 10</span><span class="sxs-lookup"><span data-stu-id="33b6d-164">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="33b6d-165">Om du använder Docker för Windows måste du dela enheten som innehåller din tillfälliga katalog (vanligt vis `C:\` enheten) med Docker daemon.</span><span class="sxs-lookup"><span data-stu-id="33b6d-165">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="33b6d-166">Mer information finns i [Docker-dokumentationen](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="33b6d-166">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="33b6d-167">När du har Docker installerat kan du antingen använda PowerShell-modulen som medföljer Quantum Development Kit-exemplen för att köra avbildningen, eller så kan du köra avbildningen manuellt.</span><span class="sxs-lookup"><span data-stu-id="33b6d-167">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="33b6d-168">Vi beskriver hur du använder PowerShell här. Om du vill använda Docker-avbildningen manuellt kan du läsa [dokumentationen som följer med avbildningen](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="33b6d-168">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="33b6d-169">Köra NWChem via PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="33b6d-169">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="33b6d-170">För att kunna använda NWChem Docker-avbildningen med Quantum Development Kit tillhandahåller vi en liten PowerShell-modul som hanterar flyttning av filer i och ut ur NWChem åt dig.</span><span class="sxs-lookup"><span data-stu-id="33b6d-170">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="33b6d-171">Om du inte redan har PowerShell Core installerat kan du ladda ned den mellan plattformar från PowerShell- [lagringsplatsen på GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="33b6d-171">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="33b6d-172">PowerShell Core används också för vissa exempel för att demonstrera samverkan med arbets flöden för data vetenskap och affärs analys.</span><span class="sxs-lookup"><span data-stu-id="33b6d-172">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="33b6d-173">När du har installerat PowerShell Core kan du importera `InvokeNWChem.psm1` för att göra NWChem-kommandon tillgängliga i den aktuella sessionen:</span><span class="sxs-lookup"><span data-stu-id="33b6d-173">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="33b6d-174">`Convert-NWChemToBroombridge`Kommandot blir tillgängligt i den aktuella PowerShell-sessionen.</span><span class="sxs-lookup"><span data-stu-id="33b6d-174">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="33b6d-175">Om du vill hämta de bilder som behövs från Docker och använda dem för att köra NWChem-inmatnings kort och avbilda utdata till Broombridge kör du följande:</span><span class="sxs-lookup"><span data-stu-id="33b6d-175">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="33b6d-176">Detta skapar en Broombridge-fil genom att köra NWChem på `input.nw` .</span><span class="sxs-lookup"><span data-stu-id="33b6d-176">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="33b6d-177">Som standard har Broombridge-utdata samma namn och sökväg som inmatnings däcket, med `.nw` tillägget ersatt av `.yaml` .</span><span class="sxs-lookup"><span data-stu-id="33b6d-177">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="33b6d-178">Detta kan åsidosättas med hjälp av `-DestinationPath` parametern till `Convert-NWChemToBroombridge` .</span><span class="sxs-lookup"><span data-stu-id="33b6d-178">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="33b6d-179">Mer information får du genom att använda PowerShell: s inbyggda hjälp funktioner:</span><span class="sxs-lookup"><span data-stu-id="33b6d-179">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
