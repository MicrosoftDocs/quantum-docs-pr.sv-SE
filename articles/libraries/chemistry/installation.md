---
title: 'Installation och verifiering av Microsoft Q # kemi Library'
description: Lär dig hur du installerar Microsoft Quantum kemi-biblioteket och använder det med NWChem-plattformen för beräknings kemi.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907366"
---
# <a name="chemistry-library-installation-and-validation"></a>Installation och verifiering av kemi-bibliotek

Quantum Development Kit har stöd för Quantum kemi-program via [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet-paketet.
Precis som med andra NuGet-paket är det enkelt att lägga till kemi-biblioteket i projektet.

**Visual Studio 2019:** Om du använder Visual Studio 2019 kan du lägga till Quantum kemi-paketen med hjälp av NuGet Package Manager.
Om du vill öppna paket hanteraren högerklickar du på det projekt som du vill lägga till kemi-biblioteket i och väljer "hantera NuGet-paket..." som i skärm bilden nedan.

![Använda NuGet Package Manager i Visual Studio 2019](~/media/vs2017-nuget-manage-packages.png)

Sök efter paket namnet "Microsoft. Quantum. kemi" från fliken Bläddra.

> [!NOTE]
> Se till att kryssa för "inkludera för hands version".

![Kryss rutan inkludera för hands version](~/media/vs2017-nuget-package-search.png)

Detta visar de paket som är tillgängliga för nedladdning.
Klicka på Microsoft. Quantum. kemi i den vänstra rutan, Välj den senaste för hands versionen i rutan till höger och klicka på "installera":

![Installera det senaste Microsoft. Quantum. kemi-paketet](~/media/vs2017-nuget-select-chem.png)

Mer information finns i UI- [guiden för paket hanteraren](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Du kan också använda Package Manager-konsolen för att lägga till Quantum kemi-biblioteket i projektet med ett kommando rads gränssnitt.

![Använda Package Manager-konsolen från kommando raden](~/media/vs2017-nuget-console-menu.png)

Kör följande från Package Manager-konsolen:

```
Install-Package Microsoft.Quantum.Chemistry
```

Mer information finns i Guide till [Package Manager-konsolen](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Kommando rad eller Visual Studio Code:** Med hjälp av kommando raden i sin egen eller från Visual Studio Code, kan du använda kommandot `dotnet` för att lägga till NuGet-paket referens i projektet:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Verifiera installationen 

Precis som resten av Quantum Development Kit, innehåller Quantum kemi-biblioteket ett antal fullständigt dokumenterade exempel som hjälper dig att komma igång snabbt.
Om du vill testa installationen med hjälp av dessa exempel kan du klona [huvud exempel lagrings platsen](https://github.com/Microsoft/Quantum)och sedan köra ett av exemplen.  Om du till exempel vill köra [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) exemplet:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Verifiera installationen av Quantum kemi-biblioteket med hjälp av Microsoft Visual Studio efter kloning av lagrings platsen:
    1. Öppna lösningen ChemistrySamples. SLN i kemi-mappen.  
    2. Välj exempel/1. Enkel molekyl/MolecularHydrogen som start projekt.
    3. Tryck på F5 för att köra uppskattnings demonstrationen av den molekyliga väte-fasen.

Mer information om hur du uppskattar värdena för energi nivåer finns i avsnittet [Hämta uppskattningar av energi nivå](xref:microsoft.quantum.chemistry.examples.energyestimate) .   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Använda Quantum Development Kit med NWChem ##

MolecularHydrogen-exemplet använder molekyliska indata som har kon figurer ATS manuellt.  Även om det här är bra för små exempel kräver Quantum kemi i skala Hamiltonians med miljon tals eller miljarder villkor. Sådan Hamiltonians, som genereras av skalbara beräknings kemi paket, är för stora för att kunna importeras manuellt. 

Quantum kemi-biblioteket för Quantum Development Kit är utformat för att fungera bra med data kemi-paket, främst i [**NWChem**](http://www.nwchem-sw.org/) -miljön för beräknings vetenskap som utvecklats av EMSL (Environment Molekyle Science Science) på Stilla havs-och Stilla havs området.
I synnerhet tillhandahåller `Microsoft.Quantum.Chemistry`-paketet verktyg för att läsa in instanser av Quantum kemi-simulerings problem som representeras i [Broombridge-schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), vilket också stöds för export av de senaste versionerna av NWChem.

För att komma igång med NWChem tillsammans med Quantum Development Kit föreslår vi en av följande metoder:
- Kom igång med att använda befintliga Broombridge-filer som finns i exemplen på [IntegralData/yaml](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Använd [EMSL Arrows Builder för Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) som är en webbaserad frontend-fil till NWChem, för att generera nya Broombridge-formaterade molekyl indatafiler.  
- Använd [Docker-avbildningen](https://hub.docker.com/r/nwchemorg/nwchem-qc/) som tillhandahålls av PNNL för att köra NWChem, eller
- [Kompilera NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) för din plattform.

I [slut punkt till slut punkt med NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) finns mer information om hur du arbetar med NWChem till kemiska modeller för att analysera med Quantum-biblioteket i Quantum utvecklaman-paketet.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Komma igång med Broombridge-filer som ingår i exemplen

Mappen [IntegralData/yaml](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) i exempel databasen i Quantum Development Kit innehåller Broombridge-formaterade molekyl data filer.  

Som ett enkelt exempel kan du använda exempel biblioteket kemi Library, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) för att läsa in Hamiltonian från en av Broombridge-filerna och utföra grind uppskattningar av Quantum simulering algorigthms:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Mer information om hur du matar in molekyler som representeras av Broombridge-schemat finns i [läsa in en Hamiltonian från en fil](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Se [Erhåll resurs antal](xref:microsoft.quantum.chemistry.examples.resourcecounts) för mer information om resurs uppskattning.  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Komma igång med EMSL Arrows Builder

EMSL-pilarna är ett verktyg som använder NWChem och kemiska beräknings databaser för att generera molekyl data.  Med [EMSL Arrows Builder för Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) kan du ange din modell med flera molekyl modell byggare och generera Broombridge-datafilen som ska användas av Quantum Development Kit.  

På sidan EMSL klickar du på fliken ["instuctions"] och följer instruktionerna för ["enkla exempel"] för att skapa Broombridge-filer.  Försök sedan att köra [' GetGateCount '] för att se Quantum Resource-uppskattningarna för dessa molekyler.

### <a name="installing-nwchem-from-source"></a>Installerar NWChem från källan

Fullständiga instruktioner för hur du installerar NWChem från källan finns [i PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Om du vill använda NWChem från Windows 10 är Windows-undersystemet för Linux ett bra alternativ.
> När du har installerat [Ubuntu 18,04-LTS för Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)kör du `ubuntu18.04` från din favorit-Terminal och följer anvisningarna ovan för att installera NWChem från källan.

När du har kompilerat NWChem från källan kan du köra det `yaml_driver` skriptet som medföljer NWChem för att snabbt producera Broombridge-instanser från NWChem-inmatade däck:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Med det här kommandot skapas en ny `input.yaml`-fil i Broombridge-format i din aktuella katalog.

### <a name="using-nwchem-with-docker"></a>Använda NWChem med Docker

Färdiga avbildningar för att använda NWChem är tillgängliga mellan plattformar via [Docker Hub](https://hub.docker.com).
Kom igång genom att följa Docker-installations anvisningarna för din plattform:

- [Installera Docker för Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Installera Docker för macOS](https://docs.docker.com/docker-for-mac/install/)
- [Installera Docker för Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Om du använder Docker för Windows måste du dela enheten som innehåller din tillfälliga katalog (vanligt vis är det `C:\` enheten) med Docker daemon. Mer information finns i [Docker-dokumentationen](https://docs.docker.com/docker-for-windows/#shared-drives) .

När du har Docker installerat kan du antingen använda PowerShell-modulen som medföljer Quantum Development Kit-exemplen för att köra avbildningen, eller så kan du köra avbildningen manuellt.
Vi beskriver hur du använder PowerShell här. Om du vill använda Docker-avbildningen manuellt kan du läsa [dokumentationen som följer med avbildningen](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Köra NWChem via PowerShell Core

För att kunna använda NWChem Docker-avbildningen med Quantum Development Kit tillhandahåller vi en liten PowerShell-modul som hanterar flyttning av filer i och ut ur NWChem åt dig.
Om du inte redan har PowerShell Core installerat kan du ladda ned den mellan plattformar från PowerShell- [lagringsplatsen på GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core används också för vissa exempel för att demonstrera samverkan med arbets flöden för data vetenskap och affärs analys.

När du har installerat PowerShell Core importerar du `InvokeNWChem.psm1` för att göra NWChem-kommandon tillgängliga i den aktuella sessionen:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Detta gör att `Convert-NWChemToBroombridge` kommandot är tillgängligt i den aktuella PowerShell-sessionen.
Om du vill hämta de bilder som behövs från Docker och använda dem för att köra NWChem-inmatnings kort och avbilda utdata till Broombridge kör du följande:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Detta skapar en Broombridge-fil genom att köra NWChem på `input.nw`.
Som standard har Broombridge-utdata samma namn och sökväg som inmatnings däcket, med `.nw` tillägget ersatt av `.yaml`.
Detta kan åsidosättas med hjälp av parametern `-DestinationPath` för att `Convert-NWChemToBroombridge`.
Mer information får du genom att använda PowerShell: s inbyggda hjälp funktioner:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
