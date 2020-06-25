---
title: Quantum Development Kit Toffoli-Simulator
description: Lär dig mer om Microsoft QDKe Toffoli simulator, en speciell funktion Quantum simulator som kan användas med miljon tals qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276027"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="43dd6-103">Quantum Development Kit Toffoli-Simulator</span><span class="sxs-lookup"><span data-stu-id="43dd6-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="43dd6-104">Quantum Development Kit tillhandahåller en Toffoli-simulator, som är en särskild simulator som kan simulera Quantum-algoritmer som är begränsade till X-, CNOT-och multi-styrda X-Quantum-åtgärder (all klassisk logik och beräkningar är tillgängliga).</span><span class="sxs-lookup"><span data-stu-id="43dd6-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="43dd6-105">Även om Toffoli-simulatorn är mycket mer begränsad i drift än [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator)kan den simulera mycket mer qubits.</span><span class="sxs-lookup"><span data-stu-id="43dd6-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="43dd6-106">Toffoli-simulatorn kan användas med miljon tals qubits, medan hela tillstånds simulatorn är allmänt begränsad till cirka 30.</span><span class="sxs-lookup"><span data-stu-id="43dd6-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="43dd6-107">Den kan köra och felsöka en begränsad uppsättning Quantum-algoritmer skrivna i Q # på din dator. till exempel kan Oracle som utvärderar booleska funktioner implementeras med hjälp av dessa portar och testas på olika qubits med den här simulatorn.</span><span class="sxs-lookup"><span data-stu-id="43dd6-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="43dd6-108">Den här Quantum simulatorn exponeras via `ToffoliSimulator` klassen.</span><span class="sxs-lookup"><span data-stu-id="43dd6-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="43dd6-109">Om du vill använda simulatorn skapar du bara en instans av den här klassen och skickar den till `Run` metoden för den Quantum-åtgärd som du vill köra tillsammans med resten av parametrarna:</span><span class="sxs-lookup"><span data-stu-id="43dd6-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="43dd6-110">Andra åtgärder</span><span class="sxs-lookup"><span data-stu-id="43dd6-110">Other Operations</span></span>

<span data-ttu-id="43dd6-111">`ToffoliSimulator`Stöder rotationer och Exponentiated Paulis, till exempel `R` och `Exp` , när den resulterande åtgärden är lika med `X` eller för identiteten.</span><span class="sxs-lookup"><span data-stu-id="43dd6-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="43dd6-112">Mått och assert stöds, men endast i Pauli- `Z` basen.</span><span class="sxs-lookup"><span data-stu-id="43dd6-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="43dd6-113">Observera att sannolikheten för viss mätning alltid är 0 eller 1; Det finns ingen slumpmässighet i Toffoli-simulatorn.</span><span class="sxs-lookup"><span data-stu-id="43dd6-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="43dd6-114">`DumpMachine`och `DumpRegister` stöds.</span><span class="sxs-lookup"><span data-stu-id="43dd6-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="43dd6-115">Båda utvärderar den aktuella `Z` bas statusen för varje qubit, en qubit per rad.</span><span class="sxs-lookup"><span data-stu-id="43dd6-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="43dd6-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="43dd6-116">QubitCount</span></span>

<span data-ttu-id="43dd6-117">Som standard `ToffoliSimulator` allokeras utrymme för 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="43dd6-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="43dd6-118">Om algoritmen kräver mer än så kan du ändra antalet qubit genom att ange ett värde för parametern för `qubitCount` konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="43dd6-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="43dd6-119">För varje ytterligare qubit krävs ytterligare byte av minne, så det finns ingen betydande kostnad för att uppskatta antalet qubits som du behöver.</span><span class="sxs-lookup"><span data-stu-id="43dd6-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="43dd6-120">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="43dd6-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
