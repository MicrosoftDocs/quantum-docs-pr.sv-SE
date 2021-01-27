---
title: Installation av Microsoft Q# kemi Library
description: Lär dig hur du installerar Microsoft Quantum kemi-biblioteket och använder det med NWChem-plattformen för beräknings kemi.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.installation
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d32544bbce527a376345023d5549308fd4e7c79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854086"
---
# <a name="chemistry-library-installation"></a>Installation av kemi-bibliotek

[ **MolecularHydrogen** -exemplet](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) använder molekyliska indata som har kon figurer ATS manuellt.
Även om det är bra för små exempel kräver Quantum kemi i skala Hamiltonians med miljon tals eller miljarder villkor.
Sådana Hamiltonians, som genereras av scalable data kemi-paket, är för stora för att kunna importeras manuellt.

Quantum kemi-biblioteket för Quantum Development Kit är utformat för att fungera bra med data kemi-paket, främst i [**NWChem**](http://www.nwchem-sw.org/) -miljön för beräknings vetenskap som utvecklats av EMSL (Environment Molekyle Science Science) på Stilla havs-och Stilla havs området.
I synnerhet innehåller [ **Microsoft. Quantum. kemi** -paketet](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) verktyg för att läsa in instanser av Quantum kemi-simulerings problem som representeras i [Broombridge-schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), vilket också stöds för export av de senaste versionerna av NWChem.

I Quantum Development Kits kemi Library finns också ett kommando rads verktyg `qdk-chem` för konvertering mellan äldre format och [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

I det här avsnittet beskrivs hur du använder Quantum Development Kit med antingen NWChem och Broombridge, eller äldre format och `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>Använda Quantum Development Kit med NWChem

Använd någon av följande metoder för att komma igång med NWChem tillsammans med Quantum Development Kit:

- Kom igång med att använda befintliga Broombridge-filer som finns i exemplen på [IntegralData/yaml](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).
- Använd [EMSL Arrows Builder för Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) som är en webbaserad frontend-fil till NWChem, för att generera nya Broombridge-formaterade molekyl indatafiler.  
- Använd [Docker-avbildningen](https://hub.docker.com/r/nwchemorg/nwchem-qc/) som tillhandahålls av PNNL för att köra NWChem, eller
- [Kompilera NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) för din plattform.

I [slut punkt till slut punkt med NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) finns mer information om hur du arbetar med NWChem till kemiska modeller för att analysera med Quantum-biblioteket i Quantum utvecklaman-paketet.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Komma igång med Broombridge-filer som ingår i exemplen

Mappen [IntegralData/yaml](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML) i exempel databasen i Quantum Development Kit innehåller Broombridge-formaterade molekyl data filer.  

Som ett enkelt exempel kan du använda exempel biblioteket kemi Library, [GetGateCount](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/GetGateCount) för att läsa in Hamiltonian från en av Broombridge-filerna och utföra grind uppskattningar av Quantum simulering algorigthms:

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
> När du har installerat [Ubuntu 18,04-LTS för Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)kör du `ubuntu18.04` från din favorit Terminal och följer anvisningarna ovan för att installera NWChem från källan.

När du har kompilerat NWChem från källan kan du köra `yaml_driver` skriptet som medföljer NWChem för att snabbt producera Broombridge-instanser från NWChem-inmatade däck:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Med det här kommandot skapas en ny `input.yaml` fil i Broombridge-formatet i din aktuella katalog.

### <a name="using-nwchem-with-docker"></a>Använda NWChem med Docker

Färdiga avbildningar för att använda NWChem är tillgängliga mellan plattformar via [Docker Hub](https://hub.docker.com).
Kom igång genom att följa Docker-installations anvisningarna för din plattform:

- [Installera Docker för Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Installera Docker för macOS](https://docs.docker.com/docker-for-mac/install/)
- [Installera Docker för Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Om du använder Docker för Windows måste du dela enheten som innehåller din tillfälliga katalog (vanligt vis `C:\` enheten) med Docker daemon. Mer information finns i [Docker-dokumentationen](https://docs.docker.com/docker-for-windows/#shared-drives) .

När du har Docker installerat kan du antingen använda PowerShell-modulen som medföljer Quantum Development Kit-exemplen för att köra avbildningen, eller så kan du köra avbildningen manuellt.
Vi beskriver hur du använder PowerShell här. Om du vill använda Docker-avbildningen manuellt kan du läsa [dokumentationen som följer med avbildningen](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Köra NWChem via PowerShell Core

För att kunna använda NWChem Docker-avbildningen med Quantum Development Kit tillhandahåller vi en liten PowerShell-modul som hanterar flyttning av filer i och ut ur NWChem åt dig.
Om du inte redan har PowerShell Core installerat kan du ladda ned den mellan plattformar från PowerShell- [lagringsplatsen på GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core används också för vissa exempel för att demonstrera samverkan med arbets flöden för data vetenskap och affärs analys.

När du har installerat PowerShell Core kan du importera `InvokeNWChem.psm1` för att göra NWChem-kommandon tillgängliga i den aktuella sessionen:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

`Convert-NWChemToBroombridge`Kommandot blir tillgängligt i den aktuella PowerShell-sessionen.
Om du vill hämta de bilder som behövs från Docker och använda dem för att köra NWChem-inmatnings kort och avbilda utdata till Broombridge kör du följande:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Detta skapar en Broombridge-fil genom att köra NWChem på `input.nw` .
Som standard har Broombridge-utdata samma namn och sökväg som inmatnings däcket, med `.nw` tillägget ersatt av `.yaml` .
Detta kan åsidosättas med hjälp av `-DestinationPath` parametern till `Convert-NWChemToBroombridge` .
Mer information får du genom att använda PowerShell: s inbyggda hjälp funktioner:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>Använda Quantum Development Kit med `qdk-chem`

`qdk-chem`Du kan installera genom att använda .net Core SDK på kommando raden:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

När du har installerat `qdk-chem` kan du använda `--help` alternativet för att få mer information om de funktioner som `qdk-chem` verktyget erbjuder.

Om du vill konvertera till och från Broombridge kan du använda `qdk-chem convert` kommandot:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

`qdk-chem convert`Kommandot kan också acceptera data från standar din data och skriva till standardutdata. Detta är särskilt användbart i skript och för integrering med verktyg som exporteras till äldre format.
Till exempel i Bash:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
