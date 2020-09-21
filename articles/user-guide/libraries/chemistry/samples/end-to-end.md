---
title: Exempel på NWChem Quantum program
description: Använd en NWChem-kortlek och gå igenom ett exempel på hur man hämtar antalet grindar för simulering av Quantum kemi.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 528c34ea9b28b2f9b8f9a8bad681557f44bfcdaa
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759723"
---
# <a name="end-to-end-with-nwchem"></a>Slutpunkt till slutpunkt med NWChem #

I den här artikeln går vi igenom ett exempel på hur man hämtar antalet grindar för simulering av Quantum kemi, från en [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) -kortlek.
Innan du fortsätter med det här exemplet ser du till att du har installerat Docker, efter [installations-och validerings guiden](xref:microsoft.quantum.chemistry.concepts.installation).

Mer information:
- [Struktur för NWChem-inmatade däck](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Kommandon för indataports kort som används med Quantum Development Kit](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [Installera kemi-biblioteket och-beroenden](xref:microsoft.quantum.chemistry.concepts.installation)
- [Resurs inventering](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Det här exemplet kräver att Windows PowerShell Core körs.
> Hämta PowerShell Core för Windows, macOS eller Linux på https://github.com/PowerShell/PowerShell .

## <a name="importing-required-powershell-modules"></a>Importerar nödvändiga PowerShell-moduler ##

Om du inte redan gjort det, klona [Microsoft/Quantum-lagringsplatsen](https://github.com/Microsoft/Quantum), som innehåller exempel och verktyg för att arbeta med Quantum Development Kit:

```powershell
git clone https://github.com/Microsoft/Quantum
```

När du har klonat `Microsoft/Quantum` , kan du utföra `cd` i `utilities/` mappen och importera PowerShell-modulen för att arbeta med Docker och NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Som standard förhindrar Windows körning av skript eller moduler som säkerhets mått.
> Om du vill tillåta moduler som `Invoke-NWChem.psm1` att köras i Windows kan du behöva ändra körnings principen.
> Det gör du genom att köra `Set-ExecutionPolicy` kommandot:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Körnings principen kommer sedan att återställas när du avslutar PowerShell.
> Om du vill spara körnings principen använder du ett annat värde för `-Scope` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Du bör nu ha `Convert-NWChemToBroombridge` kommandot tillgängligt:

```powershell
Get-Command -Module InvokeNWChem
```

Nu ska vi importera `Get-GateCount` kommandot som medföljer **GetGateCount** -exemplet.
Fullständig information finns i [instruktionerna som medföljer exemplet](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).
Kör sedan följande och Ersätt `<runtime>` med antingen `win10-x64` , `osx-x64` eller `linux-x64` , beroende på vilket operativ system du har:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Du bör nu ha `Get-GateCount` kommandot tillgängligt:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Inmatade däck ##

NWChem-paketet tar en textfil med namnet en _Indatamask_ som anger ett Quantum kemi-problem som ska lösas, tillsammans med andra parametrar, till exempel inställningar för minnesallokering.
I det här exemplet använder vi en av de färdiga ingångs kort som medföljer NWChem.
Först klonar du [nwchemgit/nwchem-lagringsplatsen](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Eftersom det här är en mycket stor lagrings plats kan vi göra en ytlig kloning för att spara viss bandbredd och disk utrymme med `--depth 1` argumentet.
> Detta är valfritt, men.
> Kloningen fungerar alldeles bra utan `--depth 1` .

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

`nwchemgit/nwchem`Lagrings platsen innehåller en mängd olika ingångs kort som är avsedda att användas med Quantum Development Kit, som visas under [ `QA/chem_library_tests` mappen](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).
I det här exemplet använder vi `H4` Indataporten:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

Molekylen i fråga är ett system av 4 väte-atomer som är ordnade i en viss geometri som är beroende av en vinkel, parametern `alpha` som anges i `h4_sto6g_alpha.nw` däckets namn. H4 är ett känt [molekyl prestandatest](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) för beräknings kemi sedan 1970s. -Parametern `sto6g` är en indikation på att däcket implementerar en representation med avseende på en Slater orbital, särskilt en representation med avseende på en [sluta-naturgas](https://en.wikipedia.org/wiki/STO-nG_basis_sets) som är inställd på 6 Gaussisk bas funktioner. Den här Indataporten innehåller dessutom flera instruktioner till TCE (NWChemy Contracting Engine) som Direct NWChem för att producera den information som krävs för att samar beta med Quantum Development Kit:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Producera och konsumera Broombridge-utdata från NWChem ##

Nu har du allt du behöver för att skapa och använda Broombridge-dokument.
Kör följande om du vill köra NWChem och skapa ett Broombridge-dokument för den `h4_sto6g_0.000.nw` inmatade däcken `Convert-NWChemToBroombridge` :

> [!NOTE]
> Första gången du kör det här kommandot kommer Docker att ladda ned `nwchemorg/nwchem-qc` avbildningen åt dig.
> Detta kan ta lite tid, beroende på din anslutnings hastighet, vilket kan ge en kopp kaffe.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Detta kommer att skapa ett Broombridge-dokument med namnet `h4_sto6g_0.000.yaml` som du kan använda med `Get-GateCount` :

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Nu bör du se konsol utdata som innehåller resurs uppskattning, t. ex. T-Count, rotationer, antal CNOT osv. för olika Quantum simulerings metoder:

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

Det finns många saker att gå härifrån: 
- Prova olika fördefinierade matnings kort, t. ex. genom att variera parametern `alpha` i `h4_sto6g_alpha.nw` 
- Försök att ändra däcken genom att redigera NWChem-däcken direkt, t. ex. utforska `STO-nG` modeller för olika val av n, 
- Testa andra fördefinierade NWChem-indatamasker som är tillgängliga på `nwchem/qa/chem_library_tests` ,
- Testa en uppsättning fördefinierade Broombridge YAML-benchmarks som genererats från NWChem och är tillgängliga som en del av [Microsoft/Quantum-lagringsplatsen](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML). Följande riktmärken är: 
    - små molekyler som molekyl väte (H2), Beryllium (vara), litium Hydride (LiH).
    - större molekyler som ozon (O3), beta-carotene, cytosine och många fler. 
- Testa de grafiska frontend- [EMSL pilar](https://arrows.emsl.pnnl.gov/api/qsharp_chem) som innehåller ett gränssnitt till Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Produktion av Broombridge-utdata från EMSL-pilar ##

Kom igång med webbaserade EMSL-pilar genom att navigera i en webbläsare [här](https://arrows.emsl.pnnl.gov/api/qsharp_chem). 

> [!NOTE]
> Att köra EMSL-pilar i en webbläsare kräver att Java Script är aktiverat. Se de här [anvisningarna](https://www.enable-javascript.com/) för hur du aktiverar java script i webbläsaren. 

Börja med att ange en molekyl i rutan fråga som säger ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Du kan ange många molekyler efter sitt colloquial namn, till exempel "Caffeine" i stället för "1, 3, 7-Trimethylxanthine". 

Klicka sedan på knappen med texten ``theory{qsharp_chem}`` . Då fylls rutan fråga i ytterligare med en instruktion som talar om för körningen att exportera utdata i Broombridge YAML-formatet. 

Klockan nu ``Run Arrows`` . Det kan ta en stund, beroende på storleken på indatatypen. Eller, om den specifika modellen redan har beräknats tidigare, kan det göras mycket snabbt eftersom det bara är ett belopp för en sökning i en databas. I båda fallen kommer du att gå till en ny sida som innehåller en mängd olika med information om den specifika körningen av NWChem mot den kortlek som anges av din indata. 

Du kan hämta och spara filen Broombridge YAML från avsnittet som börjar med följande huvud: 
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

Klicka på ``download`` , som sparar en lokal kopia med ett unikt fil namn, t ``qsharp_chem48443.yaml`` . ex. (det specifika namnet kommer att vara olika för varje körning). Du kan sedan bearbeta den här filen som ovan, t. ex. med 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
för att få resurs antal. 

Du kan njuta av 3D-molekyl Builder som kan nås från ``Arrows Entry - 3D Builder`` fliken på Start sidan för EMSL-pilarna. Om du klickar på 3D-bilden [JSMol](http://wiki.jmol.org/index.php/JSmol) på den visade molekylen kan du redigera den. Du kan flytta atomer runt, dra på atomerna så att deras mellan molekyliga avstånd förändras, Lägg till/ta bort atomer osv. För vart och ett av dessa val kan du när du har lagt till ``theory{qsharp_chem}`` i rutan fråga generera en instans av BROOMBRIDGE yaml-schemat och utforska det ytterligare med hjälp av Quantum kemi-biblioteket. 
