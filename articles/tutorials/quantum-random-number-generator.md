---
title: Skapa en kvantgenerator för slumptal
description: Skapa ett Q# projekt som visar grundläggande Quantum-koncept som överposition genom att skapa en Quantum slump tals Generator.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8db892091794cb1166e41744572d8938d975abf2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869774"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Självstudier: Implementera en kvantgenerator för slumptal i Q\#

Ett enkelt exempel på en Quantum-algoritm som Q# är skrivet i är en Quantum slump tals Generator. Den här algoritmen använder kvantmekanik till att generera ett slumptal.

## <a name="prerequisites"></a>Krav

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Skapa ett Q# projekt för att antingen [använda Q# från kommando raden](xref:microsoft.quantum.install.standalone)eller med ett [python-värdprogram](xref:microsoft.quantum.install.python) eller [C#-värd program](xref:microsoft.quantum.install.cs).

## <a name="write-a-no-locq-operation"></a>Skriv en Q# åtgärd

### <a name="no-locq-operation-code"></a>Q#åtgärds kod

1. Ersätt innehållet i filen Program.qs med följande kod:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Som vi nämnde i artikeln [Så här fungerar kvantberäkning](xref:microsoft.quantum.overview.understanding) är en kvantbit en enhet för kvantinformation som kan vara i superposition. När den mäts kan kvantbiten endast vara antingen 0 eller 1. Under körningen representerar dock tillståndet för kvantbiten sannolikheten för att avläsningen blir antingen 0 eller 1 vid en mätning. Detta sannolikhetstillstånd kallas för superposition. Vi kan använda sannolikheten till att generera slumpmässiga tal.

I vår Q# åtgärd introducerar vi `Qubit` data typen, intern för Q# . Vi kan bara allokera en `Qubit` med en `using`-instruktion. När den tilldelas är kvantbiten alltid  i `Zero`-tillståndet. 

Med hjälp av `H`-åtgärden kan vi försätta vår `Qubit` i superposition. Om du vill mäta en kvantbit och läsa dess värde, använder du den inbäddade `M`-åtgärden.

Genom att försätta vår `Qubit` i superposition och mäta den, kommer vårt resultat att bli ett annat värde varje gången koden anropas.

När en `Qubit` har frigjorts måste den försättas i `Zero`-tillståndet igen. Annars rapporteras ett körningsfel i simulatorn. Ett enkelt sätt att göra detta på är att anropa `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualisera koden med Bloch-sfären

I Bloch-sfären representerar nordpolen det klassiska värdet **0** och sydpolen det klassiska värdet **1**. Alla superpositioner kan representeras av en punkt på sfären (visas med en pil). Ju närmare pilen är en pol, desto högre är sannolikheten att kvantbiten minimeras till det klassiska värde som tilldelades till polen när den mättes. Kvantbitstillståndet som representeras av den röda pilen nedan har till exempel en högre sannolikhet att ge värdet **0** om vi mäter det.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Vi kan använda den här representationen till att visualisera vad koden gör:

* Först börjar vi med en kvantbit som initierats i tillståndet **0**. Vi använder `H` till att skapa en superposition där sannolikheten för **0** och **1** är densamma.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Sedan mäter vi kvantbiten och sparar utdatan:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Eftersom resultatet av mätningen är helt slumpmässigt har vi fått en slumpmässig bit. Vi kan anropa den här åtgärden flera gånger för att skapa heltal. Om vi till exempel anropar åtgärden tre gånger för att få tre slumpmässiga bitar, kan vi bygga slumpmässiga 3-bitarstal (det vill säga ett slumptal mellan 0 och 7).


## <a name="creating-a-complete-random-number-generator"></a>Skapa en komplett slumptalsgenerator

Nu när vi har en Q# åtgärd som genererar slumpmässiga bitar kan vi använda den för att bygga en komplett Quantum slump tals Generator. Vi kan använda Q# kommando rads program eller använda ett värd program.



### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Q#kommando rads program med Visual Studio eller Visual Studio Code](#tab/tabid-qsharp)

Om du vill skapa ett fullständigt Q# kommando rads program lägger du till följande start punkt i Q# programmet: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Den körbara filen kör åtgärden eller funktionen som har markerats med attributet `@EntryPoint()` i en simulator eller i ett resursuppskattningsverktyg, beroende på projektkonfigurationen och kommandoradsalternativen.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

Tryck bara på Ctrl+F5 i Visual Studio för att köra skriptet.

Skapa Program.qs första gången genom att skriva följande i terminalfönstret i VS Code:

```dotnetcli
dotnet build
```

För efterföljande körningar behöver du inte bygga det igen. Du kör det bara genom att skriva följande kommando och trycka på Retur:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python med Visual Studio Code eller kommandoraden](#tab/tabid-python)

Om du vill köra det nya Q# programmet från python sparar du följande kod som `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Du kan sedan köra Python-värdprogrammet från kommandoraden:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# med Visual Studio Code eller Visual Studio](#tab/tabid-csharp)

Om du vill köra det nya Q# programmet från C# ändrar `Driver.cs` du till att inkludera följande C#-kod:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Sedan kan du köra C#-värdprogrammet från kommandoraden (i Visual Studio trycker du på F5):

```bash
$ dotnet run
The random number generated is 42
```

***
