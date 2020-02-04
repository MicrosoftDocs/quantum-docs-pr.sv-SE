---
title: Skapa en kvantgenerator för slumptal
description: Skapa ett Q#-projekt som demonstrerar grundläggande kvantbegrepp som t.ex. superposition genom att skapa en kvantgenerator för slumptal.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820948"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Snabbstart: Implementera en kvantgenerator för slumptal i Q#
Ett enkelt exempel på en kvantalgoritm som skrivs i Q# och som är en kvantgenerator för slumptal. Den här algoritmen använder kvantmekanik till att generera ett slumptal. 

## <a name="prerequisites"></a>Krav

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Skapa ett Q#-projekt](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Skriv en Q#-åtgärd

### <a name="q-operation-code"></a>Q#-åtgärdskod

1. Ersätt innehållet i filen Operation.qs med följande kod:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

Som vi nämnde i artikeln [Vad är kvantberäkning?](xref:microsoft.quantum.overview.what) är en kvantbit en enhet av kvantinformation som kan vara i superposition. När den mäts kan kvantbiten endast vara antingen 0 eller 1. Under körningen representerar dock tillståndet för kvantbiten sannolikheten för att avläsningen blir antingen 0 eller 1 vid en mätning. Detta sannolikhetstillstånd kallas för superposition. Vi kan använda sannolikheten till att generera slumpmässiga tal.

I vår Q#-åtgärd introducerar vi `Qubit`-datatypen, som ingår i Q#. Vi kan bara allokera en `Qubit` med en `using`-instruktion. När den tilldelas är kvantbiten alltid  i `Zero`-tillståndet. 

Med hjälp av `H`-åtgärden kan vi försätta vår `Qubit` i superposition. Om du vill mäta en kvantbit och läsa dess värde, använder du den inbäddade `M`-åtgärden.

Genom att försätta vår `Qubit` i superposition och mäta den, kommer vårt resultat att bli ett annat värde varje gången koden anropas. 

När en `Qubit` har frigjorts måste den försättas i `Zero`-tillståndet igen, annars rapporteras ett körningsfel i simulatorn. Ett enkelt sätt att göra detta på är att anropa `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualisera koden med Bloch-sfären

I Bloch-sfären representerar nordpolen det klassiska värdet **0** och sydpolen det klassiska värdet **1**. Alla superpositioner kan representeras av en punkt på sfären (visas med en pil). Ju närmare pilen är en pol, desto högre är sannolikheten att kvantbiten minimeras till det klassiska värde som tilldelades till polen när den mättes. Kvantbitstillståndet som representeras av den röda pilen nedan har till exempel en högre sannolikhet att ge värdet **0** om vi mäter det.

<img src="~/media/qrng-Bloch.png" width="175">

Vi kan använda den här representationen till att visualisera vad koden gör:

* Först börjar vi med en kvantbit som initierats i tillståndet **0**. Vi använder `H` till att skapa en superposition där sannolikheten för **0** och **1** är densamma.

<img src="~/media/qrng-H.png" width="450">

* Sedan mäter vi kvantbiten och sparar utdatan:

<img src="~/media/qrng-meas.png" width="450">

Eftersom resultatet av mätningen är helt slumpmässigt har vi fått en slumpmässig bit. Vi kan anropa den här åtgärden flera gånger för att skapa heltal. Om vi till exempel anropar åtgärden tre gånger för att få tre slumpmässiga bitar, kan vi bygga slumpmässiga 3-bitarstal (det vill säga ett slumptal mellan 0 och 7).

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Skapa en komplett slumptalsgenerator med ett värdprogram

Nu när vi har en Q#-åtgärd som genererar slumpmässiga bitar, kan vi använda den till att skapa en komplett slumptalsgenerator med ett värdprogram.

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[Python med Visual Studio Code eller kommandoraden](#tab/tabid-python)
 
 Om du vill köra ditt nya Q#-program från Python sparar du följande kod som `host.py`:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 Du kan sedan köra Python-värdprogrammet från kommandoraden:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[C# med Visual Studio Code eller kommandoraden](#tab/tabid-csharp)
 
 Om du vill köra ditt nya Q#-program från C# ändrar du `Driver.cs` så att följande C#-kod ingår:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 Du kan sedan köra C#-värdprogrammet från kommandoraden:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[C# med Visual Studio 2019](#tab/tabid-vs2019)

 Om du vill köra ditt nya Q#-program från C# i Visual Studio ändrar du `Driver.cs` så att följande C#-kod ingår:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Därefter trycker du på F5. Programmet startas och ett nytt fönster öppnas med det genererade slumptalet: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
