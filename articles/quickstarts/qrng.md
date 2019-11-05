---
title: Skapa en kvantgenerator för slumptal
description: Skapa ett Q#-projekt som demonstrerar grundläggande kvantbegrepp som t.ex. superposition genom att skapa en kvantgenerator för slumptal.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443927"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Snabbstart: Implementera en kvantgenerator för slumptal i Q#
Ett enkelt exempel på en kvantalgoritm som skrivs i Q# och som är en kvantgenerator för slumptal. Den här algoritmen använder kvantmekanik till att generera ett slumptal. 

## <a name="prerequisites"></a>Nödvändiga komponenter

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Skapa ett Q#-projekt](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Skriv en Q#-åtgärd

### <a name="q-operation-code"></a>Q#-åtgärdskod

1. Ersätt innehållet i filen Operation.qs med följande kod:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
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

<img src="./Bloch.svg" width="175">

Vi kan använda den här representationen till att visualisera vad koden gör:

* Först börjar vi med en kvantbit som initierats i tillståndet **0**. Vi använder `H` till att skapa en superposition där sannolikheten för **0** och **1** är densamma.

<img src="./H.svg" width="450">

* Sedan mäter vi kvantbiten och sparar utdatan:

<img src="./Measurement2.svg" width="450">

Eftersom resultatet av mätningen är helt slumpmässigt har vi fått en slumpmässig bit. Vi kan anropa den här funktionen flera gånger för att skapa heltal. Om vi till exempel anropar funktionen tre gånger för att få tre slumpmässiga bitar, kan vi bygga slumpmässiga 3-bitarstal (det vill säga ett slumptal mellan 0 och 7).
