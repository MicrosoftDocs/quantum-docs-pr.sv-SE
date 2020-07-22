---
title: Quantum Toffoli Simulator – Quantum Development Kit
description: Lär dig mer om Microsoft QDKe Toffoli simulator, en speciell funktion Quantum simulator som kan användas med miljon tals qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870625"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="b2371-103">Toffoli Simulator för Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b2371-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="b2371-104">QDK Toffoli-simulatorn är en särskild simulator med en begränsad omfattning och stöder bara `X` , `CNOT` och flera kontrollerade `X` Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b2371-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="b2371-105">All klassisk logik och alla beräkningar är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="b2371-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="b2371-106">Även om Toffoli-simulatorn är mer begränsad i funktionalitet än med [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), har den fördelen att kunna simulera mycket mer qubits.</span><span class="sxs-lookup"><span data-stu-id="b2371-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="b2371-107">Toffoli-simulatorn kan användas med miljon tals qubits, medan hela tillstånds simulatorn är begränsad till cirka 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="b2371-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="b2371-108">Detta är användbart, till exempel med Oracle som utvärderar booleska funktioner – de kan implementeras med den begränsade uppsättningen algoritmer som stöds och testas på ett stort antal qubits.</span><span class="sxs-lookup"><span data-stu-id="b2371-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="b2371-109">Anropar Toffoli-simulatorn</span><span class="sxs-lookup"><span data-stu-id="b2371-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="b2371-110">Du exponerar Toffoli-simulatorn via- `ToffoliSimulator` klassen.</span><span class="sxs-lookup"><span data-stu-id="b2371-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="b2371-111">Mer information finns i [sätt att köra ett Q #-program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b2371-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="b2371-112">Anropar Toffoli-simulatorn från C #</span><span class="sxs-lookup"><span data-stu-id="b2371-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="b2371-113">Precis som med andra mål datorer skapar du först en instans av `ToffoliSimulator` klassen och skickar den som den första parametern för en åtgärds `Run` metod.</span><span class="sxs-lookup"><span data-stu-id="b2371-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b2371-114">Observera att om klassen till skillnad från `QuantumSimulator` klassen `ToffoliSimulator` implementerar inte <xref:System.IDisposable> gränssnittet, och därför behöver du inte ange det i en `using` instruktion.</span><span class="sxs-lookup"><span data-stu-id="b2371-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="b2371-115">Anropar Toffoli-simulatorn från python</span><span class="sxs-lookup"><span data-stu-id="b2371-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="b2371-116">Använd metoden [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q #-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="b2371-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="b2371-117">Anropar Toffoli-simulatorn från kommando raden</span><span class="sxs-lookup"><span data-stu-id="b2371-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="b2371-118">När du kör ett Q #-program från kommando raden använder du parametern **--Simulator** (eller **-s** Shortcut) för att ange Toffoli Simulator mål dator.</span><span class="sxs-lookup"><span data-stu-id="b2371-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="b2371-119">Följande kommando kör ett program med hjälp av resurs uppskattningen:</span><span class="sxs-lookup"><span data-stu-id="b2371-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="b2371-120">Anropar Toffoli-simulatorn från Juptyer Notebooks</span><span class="sxs-lookup"><span data-stu-id="b2371-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="b2371-121">Använd SWEETIQ # Magic kommandot [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) för att köra Q #-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="b2371-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="b2371-122">Åtgärder som stöds</span><span class="sxs-lookup"><span data-stu-id="b2371-122">Supported operations</span></span>

<span data-ttu-id="b2371-123">Toffoli Simulator stöder:</span><span class="sxs-lookup"><span data-stu-id="b2371-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="b2371-124">Rotationer och exponentiated Paulis, till exempel `R` och `Exp` , när den resulterande åtgärden är lika med `X` eller identitets mat ris.</span><span class="sxs-lookup"><span data-stu-id="b2371-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="b2371-125">Mått och [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) -åtgärder, men endast i Pauli- `Z` basen.</span><span class="sxs-lookup"><span data-stu-id="b2371-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="b2371-126">Observera att sannolikheten för en mått åtgärd alltid är **0** eller **1**; Det finns ingen slumpmässighet i Toffoli-simulatorn.</span><span class="sxs-lookup"><span data-stu-id="b2371-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="b2371-127">`DumpMachine`och- `DumpRegister` funktioner.</span><span class="sxs-lookup"><span data-stu-id="b2371-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="b2371-128">Båda funktionerna utvärderar aktuell `Z` bas status för varje qubit, en qubit per rad.</span><span class="sxs-lookup"><span data-stu-id="b2371-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="b2371-129">Ange antalet qubits</span><span class="sxs-lookup"><span data-stu-id="b2371-129">Specifying the number of qubits</span></span>

<span data-ttu-id="b2371-130">Som standard `ToffoliSimulator` allokerar en instans utrymme för 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="b2371-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="b2371-131">Om algoritmen kräver mer qubits kan du ange antalet qubit genom att ange ett värde för `qubitCount` parametern för konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="b2371-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="b2371-132">För varje ytterligare qubit krävs bara en byte av minne, så det finns ingen betydande kostnad för att uppskatta antalet qubits som du behöver.</span><span class="sxs-lookup"><span data-stu-id="b2371-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="b2371-133">Exempel:</span><span class="sxs-lookup"><span data-stu-id="b2371-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="b2371-134">Se även</span><span class="sxs-lookup"><span data-stu-id="b2371-134">See also</span></span>

- [<span data-ttu-id="b2371-135">Uppskattning av Quantum-resurser</span><span class="sxs-lookup"><span data-stu-id="b2371-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="b2371-136">Quantum trace Simulator</span><span class="sxs-lookup"><span data-stu-id="b2371-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="b2371-137">Quantum, fullständig tillstånds Simulator</span><span class="sxs-lookup"><span data-stu-id="b2371-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 