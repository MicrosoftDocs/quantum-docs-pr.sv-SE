---
title: Slut punkt till slut punkt med NWChem | Microsoft Docs
description: Slut punkt till slut punkt med NWChem-dokument
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185825"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="187e7-103">Slut punkt till slut punkt med NWChem</span><span class="sxs-lookup"><span data-stu-id="187e7-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="187e7-104">På den här sidan går vi igenom ett exempel på hur man hämtar antalet grindar för simulering av Quantum kemi, från en [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) -kortlek.</span><span class="sxs-lookup"><span data-stu-id="187e7-104">In this page, we will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="187e7-105">Innan du fortsätter med det här exemplet ser du till att du har installerat Docker, efter [installations-och validerings guiden](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="187e7-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="187e7-106">Mer information:</span><span class="sxs-lookup"><span data-stu-id="187e7-106">For more information:</span></span>
- [<span data-ttu-id="187e7-107">Struktur för NWChem-inmatade däck</span><span class="sxs-lookup"><span data-stu-id="187e7-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="187e7-108">Kommandon för indataports kort som används med Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="187e7-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="187e7-109">Installera kemi-biblioteket och-beroenden</span><span class="sxs-lookup"><span data-stu-id="187e7-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="187e7-110">Resurs inventering</span><span class="sxs-lookup"><span data-stu-id="187e7-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="187e7-111">Det här exemplet kräver att Windows PowerShell Core körs.</span><span class="sxs-lookup"><span data-stu-id="187e7-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="187e7-112">Hämta PowerShell Core för Windows, macOS eller Linux på https://github.com/PowerShell/PowerShell.</span><span class="sxs-lookup"><span data-stu-id="187e7-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="187e7-113">Importerar nödvändiga PowerShell-moduler</span><span class="sxs-lookup"><span data-stu-id="187e7-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="187e7-114">Om du inte redan gjort det, klona [Microsoft/Quantum-lagringsplatsen](https://github.com/Microsoft/Quantum), som innehåller exempel och verktyg för att arbeta med Quantum Development Kit:</span><span class="sxs-lookup"><span data-stu-id="187e7-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="187e7-115">När du har klonat `Microsoft/Quantum`, utför `cd` i `utilities/`-mappen och importera PowerShell-modulen för att arbeta med Docker och NWChem:</span><span class="sxs-lookup"><span data-stu-id="187e7-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="187e7-116">Som standard förhindrar Windows körning av skript eller moduler som säkerhets mått.</span><span class="sxs-lookup"><span data-stu-id="187e7-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="187e7-117">Om du vill tillåta moduler som `Invoke-NWChem.psm1` att köras i Windows kan du behöva ändra körnings principen.</span><span class="sxs-lookup"><span data-stu-id="187e7-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="187e7-118">Det gör du genom att köra kommandot `Set-ExecutionPolicy`:</span><span class="sxs-lookup"><span data-stu-id="187e7-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="187e7-119">Körnings principen kommer sedan att återställas när du avslutar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="187e7-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="187e7-120">Om du vill spara körnings principen använder du ett annat värde för `-Scope`:</span><span class="sxs-lookup"><span data-stu-id="187e7-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="187e7-121">Du bör nu ha kommandot `Convert-NWChemToBroombridge` tillgängligt:</span><span class="sxs-lookup"><span data-stu-id="187e7-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="187e7-122">Nu ska vi importera kommandot `Get-GateCount` som tillhandahålls med **GetGateCount** -exemplet.</span><span class="sxs-lookup"><span data-stu-id="187e7-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="187e7-123">Fullständig information finns i [instruktionerna som medföljer exemplet](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="187e7-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span></span>
<span data-ttu-id="187e7-124">Kör sedan följande och ersätt `<runtime>` med antingen `win10-x64`, `osx-x64`eller `linux-x64`, beroende på vilket operativ system du har:</span><span class="sxs-lookup"><span data-stu-id="187e7-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="187e7-125">Du bör nu ha kommandot `Get-GateCount` tillgängligt:</span><span class="sxs-lookup"><span data-stu-id="187e7-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="187e7-126">Inmatade däck</span><span class="sxs-lookup"><span data-stu-id="187e7-126">Input Decks</span></span> ##

<span data-ttu-id="187e7-127">NWChem-paketet tar en textfil med namnet en _Indatamask_ som anger ett Quantum kemi-problem som ska lösas, tillsammans med andra parametrar, till exempel inställningar för minnesallokering.</span><span class="sxs-lookup"><span data-stu-id="187e7-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="187e7-128">I det här exemplet använder vi en av de färdiga ingångs kort som medföljer NWChem.</span><span class="sxs-lookup"><span data-stu-id="187e7-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="187e7-129">Först klonar du [nwchemgit/nwchem-lagringsplatsen](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="187e7-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="187e7-130">Eftersom det här är en mycket stor lagrings plats kan vi göra en ytlig kloning för att spara viss bandbredd och disk utrymme med hjälp av argumentet `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="187e7-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="187e7-131">Detta är valfritt, men.</span><span class="sxs-lookup"><span data-stu-id="187e7-131">This is optional, however.</span></span>
> <span data-ttu-id="187e7-132">Kloningen fungerar alldeles bra utan `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="187e7-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="187e7-133">`nwchemgit/nwchem`-lagringsplatsen levereras med en mängd olika ingångs kort som är avsedda att användas med Quantum Development Kit, som visas under [mappen`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="187e7-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="187e7-134">I det här exemplet använder vi `H4` däck:</span><span class="sxs-lookup"><span data-stu-id="187e7-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="187e7-135">Molekylen i fråga är ett system av 4 väte-atomer som är ordnade i en viss geometri som är beroende av en vinkel, parametern `alpha` som anges i däckets namn `h4_sto6g_alpha.nw`.</span><span class="sxs-lookup"><span data-stu-id="187e7-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="187e7-136">H4 är ett känt [molekyl prestandatest](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) för beräknings kemi sedan 1970s.</span><span class="sxs-lookup"><span data-stu-id="187e7-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="187e7-137">Parametern `sto6g` är en indikation på att däcket implementerar en representation med avseende på en Slater orbital, särskilt en representation med avseende på en [sluta-naturgas](https://en.wikipedia.org/wiki/STO-nG_basis_sets) som är inställd på 6 Gaussisk bas funktioner.</span><span class="sxs-lookup"><span data-stu-id="187e7-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="187e7-138">Den här Indataporten innehåller dessutom flera instruktioner till TCE (NWChemy Contracting Engine) som Direct NWChem för att producera den information som krävs för att samar beta med Quantum Development Kit:</span><span class="sxs-lookup"><span data-stu-id="187e7-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="187e7-139">Producera och konsumera Broombridge-utdata från NWChem</span><span class="sxs-lookup"><span data-stu-id="187e7-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="187e7-140">Vi har nu allt vi behöver för att skapa och använda Broombridge-dokument.</span><span class="sxs-lookup"><span data-stu-id="187e7-140">We now have everything we need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="187e7-141">Kör `Convert-NWChemToBroombridge`för att köra NWChem och skapa ett Broombridge-dokument för `h4_sto6g_0.000.nw`-datanings däck:</span><span class="sxs-lookup"><span data-stu-id="187e7-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="187e7-142">Första gången du kör det här kommandot kommer Docker att ladda ned `nwchemorg/nwchem-qc` avbildningen åt dig.</span><span class="sxs-lookup"><span data-stu-id="187e7-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="187e7-143">Detta kan ta lite tid, beroende på din anslutnings hastighet, vilket kan ge en kopp kaffe.</span><span class="sxs-lookup"><span data-stu-id="187e7-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="187e7-144">Detta kommer att skapa ett Broombridge-dokument med namnet `h4_sto6g_0.000.yaml` som vi kan använda med `Get-GateCount`:</span><span class="sxs-lookup"><span data-stu-id="187e7-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that we can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="187e7-145">Nu bör du se konsol utdata som innehåller resurs uppskattning, t. ex. T-Count, rotationer, antal CNOT osv. för olika Quantum simulerings metoder:</span><span class="sxs-lookup"><span data-stu-id="187e7-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="187e7-146">Det finns många saker att gå härifrån:</span><span class="sxs-lookup"><span data-stu-id="187e7-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="187e7-147">Prova olika fördefinierade matnings kort, t. ex. genom att variera parametern `alpha` i `h4_sto6g_alpha.nw`,</span><span class="sxs-lookup"><span data-stu-id="187e7-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="187e7-148">Försök att ändra däcken genom att redigera NWChem-däcken direkt, t. ex., utforska `STO-nG` modeller för olika val av n,</span><span class="sxs-lookup"><span data-stu-id="187e7-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="187e7-149">Testa andra fördefinierade NWChem-indatamasker som är tillgängliga på `nwchem/qa/chem_library_tests`,</span><span class="sxs-lookup"><span data-stu-id="187e7-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="187e7-150">Testa en uppsättning fördefinierade Broombridge YAML-benchmarks som genererats från NWChem och är tillgängliga som en del av [Microsoft/Quantum-lagringsplatsen](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="187e7-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="187e7-151">Följande riktmärken är:</span><span class="sxs-lookup"><span data-stu-id="187e7-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="187e7-152">små molekyler som molekyl väte (H2), Beryllium (vara), litium Hydride (LiH).</span><span class="sxs-lookup"><span data-stu-id="187e7-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="187e7-153">större molekyler som ozon (O3), beta-carotene, cytosine och många fler.</span><span class="sxs-lookup"><span data-stu-id="187e7-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="187e7-154">Testa de grafiska frontend- [EMSL pilar](https://arrows.emsl.pnnl.gov/api/qsharp_chem) som innehåller ett gränssnitt till Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="187e7-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="187e7-155">Produktion av Broombridge-utdata från EMSL-pilar</span><span class="sxs-lookup"><span data-stu-id="187e7-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="187e7-156">Kom igång med webbaserade EMSL-pilar genom att navigera i en webbläsare [här](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span><span class="sxs-lookup"><span data-stu-id="187e7-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="187e7-157">Att köra EMSL-pilar i en webbläsare kräver att Java Script är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="187e7-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="187e7-158">Se de här [anvisningarna](https://www.enable-javascript.com/) för hur du aktiverar java script i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="187e7-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="187e7-159">Börja med att ange en molekyl i rutan fråga som säger ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="187e7-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="187e7-160">Du kan ange många molekyler efter sitt colloquial namn, till exempel "Caffeine" i stället för "1, 3, 7-Trimethylxanthine".</span><span class="sxs-lookup"><span data-stu-id="187e7-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="187e7-161">Klicka sedan på knappen med texten ``theory{qsharp_chem}``.</span><span class="sxs-lookup"><span data-stu-id="187e7-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="187e7-162">Då fylls rutan fråga i ytterligare med en instruktion som talar om för körningen att exportera utdata i Broombridge YAML-formatet.</span><span class="sxs-lookup"><span data-stu-id="187e7-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="187e7-163">Nu ska du stämpla ``Run Arrows``.</span><span class="sxs-lookup"><span data-stu-id="187e7-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="187e7-164">Det kan ta en stund, beroende på storleken på indatatypen.</span><span class="sxs-lookup"><span data-stu-id="187e7-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="187e7-165">Eller, om den specifika modellen redan har beräknats tidigare, kan det göras mycket snabbt eftersom det bara är ett belopp för en sökning i en databas.</span><span class="sxs-lookup"><span data-stu-id="187e7-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="187e7-166">I båda fallen kommer du att gå till en ny sida som innehåller en mängd olika med information om den specifika körningen av NWChem mot den kortlek som anges av din indata.</span><span class="sxs-lookup"><span data-stu-id="187e7-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="187e7-167">Du kan hämta och spara filen Broombridge YAML från avsnittet som börjar med följande huvud:</span><span class="sxs-lookup"><span data-stu-id="187e7-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="187e7-168">Klicka på ``download``, som sparar en lokal kopia med ett unikt fil namn, till exempel ``qsharp_chem48443.yaml`` (det specifika namnet kommer att vara olika för varje körning).</span><span class="sxs-lookup"><span data-stu-id="187e7-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="187e7-169">Du kan sedan bearbeta den här filen som ovan, t. ex. med</span><span class="sxs-lookup"><span data-stu-id="187e7-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="187e7-170">för att få resurs antal.</span><span class="sxs-lookup"><span data-stu-id="187e7-170">to get resource counts.</span></span> 

<span data-ttu-id="187e7-171">Du kan njuta av 3D-molekyl Builder som kan nås från fliken ``Arrows Entry - 3D Builder`` på Start sidan för EMSL-pilarna.</span><span class="sxs-lookup"><span data-stu-id="187e7-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="187e7-172">Om du klickar på 3D-bilden [JSMol](http://wiki.jmol.org/index.php/JSmol) på den visade molekylen kan du redigera den.</span><span class="sxs-lookup"><span data-stu-id="187e7-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="187e7-173">Du kan flytta atomer runt, dra på atomerna så att deras mellan molekyliga avstånd förändras, Lägg till/ta bort atomer osv. När du har lagt till ``theory{qsharp_chem}`` i rutan fråga för var och en av dessa alternativ kan du generera en instans av Broombridge YAML-schemat och utforska det ytterligare med hjälp av Quantum kemi-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="187e7-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
