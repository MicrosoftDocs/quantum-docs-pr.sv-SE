---
title: Utforma din egen klassificerare med QDK
description: Lär dig grunderna för att utforma krets modeller för den koncentriska klassificeraren i Quantum-kretsen.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 60e694e9f7c2f01a6679ef960f5a7774c8bd6a62
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868956"
---
# <a name="design-your-own-classifier"></a>Utforma din egen klassificerare

I den här guiden får du lära dig de grundläggande begreppen bakom utformningen av krets modeller för den koncentriska klassificeraren i Quantum-kretsen.

Precis som i klassisk djup inlärning finns det ingen allmän regel för att välja en speciell arkitektur. Beroende på problemet kommer vissa arkitekturer att fungera bättre än andra. Men det finns vissa begrepp som kan vara användbara när du utformar kretsen:

- Ett stort antal parametrar innebär en mer flexibel modell som kan vara lämplig för att rita komplexa klassificerings gränser, men det kan också vara mer känsligt för överanpassning.

- Entangling-portar mellan qubits är nödvändiga för att avbilda korrelationer mellan Quantum-funktionerna.

## <a name="how-to-build-a-classifier-with-q"></a>Så här skapar du en klassificerare med Q\#

För att bygga en klassificerare ska vi kombinera parametrized kontrollerade rotationer i vår krets modell. För att göra det kan vi använda den typ som [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definierats i Quantum Machine Learning-biblioteket. Den här typen accepterar fyra argument som avgör: indexet för mål-qubit, matrisen med index-qubits, rotations axeln och index för den associerade parametern i matrisen med parametrar som definierar modellen.

Nu ska vi se ett exempel på en klassificerare. I [exemplen på halv måne](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)kan vi hitta följande klassificerare som definierats i filen `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

Vad vi definierar här är en funktion som returnerar en element mat ris `ControlledRotation` , som tillsammans med en matris med parametrar och en förskjutning definierar vår [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) . Den här typen är grundläggande i Quantum Machine Learning-biblioteket och definierar klassificeraren. Den krets som definieras i funktionen ovan är en del av en klassificerare där varje exempel i data uppsättningen innehåller två funktioner. Därför behöver vi bara två qubits. Den grafiska åter givningen av kretsen är:

 ![Exempel på krets modell](~/media/circuit_model_1.PNG)

Observera att som standard åtgärder i Quantum Machine Learning-biblioteket, mäter den sista qubit i registret för att uppskatta klassificeringen sannolikhet. Tänk på detta när du utformar din krets.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Använd biblioteks funktionerna för att skriva lager med portar

Anta att vi har en data uppsättning med 784-funktioner per instans, t. ex. bilder på 28 × 28 pixlar som MNIST-datauppsättningen. I det här fallet blir kretsens bredd tillräckligt stor så att skrivning av varje enskild grind blir en möjlig men opraktisk uppgift. Detta är anledningen till att Quantum Machine Learning-biblioteket innehåller en uppsättning verktyg som automatiskt genererar lager av parametrized-rotationer. Funktionen returnerar till exempel [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) en matris med okontrollerade qubit rotationer längs en viss axel, med en rotation för varje qubit i registret, varje parametrized med en annan modell parameter. `LocalRotationsLayer(4, X)`Returnerar exempelvis följande port uppsättning:

 ![Lokalt rotations skikt](~/media/local_rotations_layer.PNG)

Vi rekommenderar att du utforskar [API-referensen för Quantum Machine Learning-biblioteket](xref:microsoft.quantum.machinelearning) för att identifiera alla verktyg som är tillgängliga för att effektivisera krets designen.

## <a name="next-steps"></a>Nästa steg

 Prova olika strukturer i exemplen som tillhandahålls av exemplen. Ser du ändringar i modellens prestanda? I nästa självstudie får [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) du lära dig hur du läser in data uppsättningar för att testa och utforska nya arkitekturer i klassificeraren.
