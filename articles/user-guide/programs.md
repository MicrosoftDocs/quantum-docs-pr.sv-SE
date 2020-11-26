---
title: 'Q # introdution'
description: 'Snabb introduktion till Quantum-program i Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234321"
---
# <a name="q-quantum-programming-language"></a>Q # Quantum programmerings språk

Allt du behöver veta om programmeringsspråket Q # beskrivs i [språk guide för q #](xref:microsoft.quantum.qsharp.index). Precis som något annat är vår [språk design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) öppen källa och vi välkomnar bidrag.
Mer bakgrund om grunderna och motivation bakom Q # finns i [Varför behöver vi Q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
Q # levereras som en del av Quantum Development Kit (QDK) för en snabb översikt, se [Vad är QDK?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Vad är ett Quantum-program?

Ett Quantum-program kan ses som en viss uppsättning klassiska under rutiner som, när de anropas, utför en beräkning genom att interagera med ett Quantum-system; ett program som är skrivet i Q # kan inte direkt modellera Quantum-tillstånd, utan beskriver i stället hur en klassisk kontroll dator interagerar med qubits.
På så sätt kan vi helt oberoende om vad ett Quantum-tillstånd *är* även på varje måldator, vilket kan ha olika tolkningar beroende på datorn. 

En viktig följd av detta är att Q # inte har möjlighet att introspect till status för en qubit eller andra egenskaper för Quantum Mechanics direkt, vilket garanterar att ett Q #-program kan köras fysiskt på en dator med en Quantum-dator.
Ett program kan i stället anropa åtgärder, till exempel [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) för att extrahera klassisk information från en qubit.

När den har allokerats kan en qubit skickas till åtgärder och funktioner, även kallat *callables*. Detta är i viss bemärkelse att ett Q #-program kan göra med en qubit; Alla direkta åtgärder för status för en qubit definieras av en *inbyggd* callables, till exempel [`X`](xref:Microsoft.Quantum.Intrinsic.X) och [`H`](xref:Microsoft.Quantum.Intrinsic.H) -dvs. callables vars implementeringar inte har definierats inom Q # men definieras i stället av mål datorn. De här *åtgärderna faktiskt görs* enbart konkret av mål datorn som vi använder för att köra ett visst Q #-program.

Om du till exempel kör programmet i en [full-State-Simulator](xref:microsoft.quantum.machines.full-state-simulator)utför simulatorn motsvarande matematiska åtgärder till det simulerade Quantum-systemet.
Men om mål datorn är en verklig Quantum-dator och du tittar på framtiden, så dirigerar de här åtgärderna i Q # den Quantum datorn för att utföra motsvarande *verkliga* åtgärder på det *verkliga* Quantum-systemet (t. ex. exakta tids bara laser pulser).

Ett Q #-program kombinerar dessa åtgärder så som definieras av en mål dator för att skapa nya, högre åtgärder för att uttrycka Quantum-beräkning.
På så sätt gör Q # det enkelt att uttrycka logiken för de underliggande Quantum-och hybrid Quantum-algoritmerna, samtidigt som det är allmänt vad gäller strukturen för en mål dator eller Simulator.

Ett enkelt exempel är följande program, som allokerar ett qubit i $ \ket {0} $-tillstånd, och sedan tillämpar en Hadamard-åtgärd `H` på den och mäter resultatet i `PauliZ` grunden.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Vår [Quantum-Katas](https://github.com/microsoft/QuantumKatas#introduction) ger en bättre introduktion till [Quantum Computing-koncept](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) som vanliga Quantum-åtgärder och hur du manipulerar qubits. Fler exempel finns även i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude).



