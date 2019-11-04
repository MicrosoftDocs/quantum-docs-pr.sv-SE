---
title: 'Q #-tekniker-lokala variabler | Microsoft Docs'
description: 'Q #-tekniker – lokala variabler'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183292"
---
# <a name="local-variables"></a>Lokala variabler #

Ett värde av valfri typ i Q # kan tilldelas en variabel för åter användning i en åtgärd eller funktion med hjälp av nyckelordet `let`.
Exempel:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Detta tilldelar en viss matris av Pauli-operatörer till en variabel som kallas `measurementOperator`.

> [!TIP]
> Observera att vi inte uttryckligen behöver ange typen av vår nya variabel, eftersom uttrycket till höger i instruktionen `let` är entydigt och att typen härleds av kompilatorn. 

Variabler i Q # är *oföränderliga*, vilket innebär att när en variabel har definierats på det här sättet kan den inte längre ändras på något sätt.
Detta möjliggör flera betalnings optimeringar, inklusive optimering av den klassiska logiken i variabler för att sorteras om för att tillämpa `Adjoint` varianten av en åtgärd.

Variabler som definieras med `let` bindning som ovan är lokala i ett visst omfång, till exempel en åtgärds brödtext eller innehållet i en `for`-slinga.


## <a name="mutability"></a>Föränderlighet ##

Som ett alternativ till att skapa en variabel med `let`skapar nyckelordet `mutable` en speciell föränderligt-variabel som kan bindas igen efter att den ursprungligen har skapats med hjälp av nyckelordet `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Alla typer i Q #, inklusive matriser, följer värde semantik. I synnerhet är det inte möjligt att uppdatera mat ris objekt. Om du vill ändra en befintlig matris måste du använda en kopierings-och-uppdatera-mekanism på samma F#sätt som för poster i. Med hjälp av biblioteks verktygen för matriser som finns i [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)kan vi enkelt definiera en funktion som returnerar en matris med Paul, där Pauli vid index `i` tar det givna värdet och alla andra poster är identiteten: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Vi kommer att utveckla mer om hur du arbetar med matriser när du diskuterar frågor och uttryck i Q #. 

Föränderlighet inom Q # är ett koncept som gäller för en *symbol* i stället för en typ eller ett värde. Mer specifikt har det inte en representation i typ systemet, implicit eller explicit, och om en bindning är föränderligt (som anges av nyckelordet `mutable`) eller oföränderligt (som anges av `let`) inte ändrar typen för de variabla variabeln (erna). Detta är ett viktigt sätt att isolera föränderlighet i specialiserade funktioner och åtgärder.
I synnerhet, även om en angränsande specialisering för en åtgärd som använder en föränderligt-variabel inte kan genereras automatiskt, fungerar automatisk generering bra för en åtgärd som anropar en funktion som använder föränderlighet.
Av den anledningen är det en bra idé att skapa funktioner och åtgärder som använder föränderlighet som kort och komprimering som möjligt, så att resten av Quantum-programmet kan skrivas med vanliga variabler som inte kan ändras.


## <a name="deconstruction"></a>Avkonstruktion ##

Förutom att tilldela en enskild variabel, `let` och `mutable` nyckelord – eller i själva verket andra bindnings konstruktioner, så att du kan packa upp innehållet i en [tuple-typ](xref:microsoft.quantum.language.type-model#tuple-types).
En tilldelning av det här formuläret är att *avkonstruera* elementen i denna tupel.
Om vi till exempel modellerar en term i en Hamiltonian av en tupel, kan vi använda den för att få åtkomst till de olika data som vi behöver simulera under den perioden:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


