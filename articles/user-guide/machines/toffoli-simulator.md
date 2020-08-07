---
title: Quantum Toffoli Simulator – Quantum Development Kit
description: Lär dig mer om Microsoft QDKe Toffoli simulator, en speciell funktion Quantum simulator som kan användas med miljon tals qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8a981645703423856e667be7c3dccf5270a5885f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868108"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="d1e5a-103">Toffoli Simulator för Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="d1e5a-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="d1e5a-104">QDK Toffoli-simulatorn är en särskild simulator med en begränsad omfattning och stöder bara `X` , `CNOT` och flera kontrollerade `X` Quantum-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="d1e5a-105">All klassisk logik och alla beräkningar är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="d1e5a-106">Även om Toffoli-simulatorn är mer begränsad i funktionalitet än med [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), har den fördelen att kunna simulera mycket mer qubits.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="d1e5a-107">Toffoli-simulatorn kan användas med miljon tals qubits, medan hela tillstånds simulatorn är begränsad till cirka 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="d1e5a-108">Detta är användbart, till exempel med Oracle som utvärderar booleska funktioner – de kan implementeras med den begränsade uppsättningen algoritmer som stöds och testas på ett stort antal qubits.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="d1e5a-109">Anropar Toffoli-simulatorn</span><span class="sxs-lookup"><span data-stu-id="d1e5a-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="d1e5a-110">Du exponerar Toffoli-simulatorn via- `ToffoliSimulator` klassen.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="d1e5a-111">Mer information finns i [sätt att köra ett Q# program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="d1e5a-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="d1e5a-112">Anropar Toffoli-simulatorn från C #</span><span class="sxs-lookup"><span data-stu-id="d1e5a-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="d1e5a-113">Precis som med andra måldatorer skapar du först en instans av klassen `ToffoliSimulator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="d1e5a-114">Observera att i motsats till `QuantumSimulator`-klassen implementerar `ToffoliSimulator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="d1e5a-115">Anropar Toffoli-simulatorn från python</span><span class="sxs-lookup"><span data-stu-id="d1e5a-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="d1e5a-116">Använd metoden [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q# åtgärden:</span><span class="sxs-lookup"><span data-stu-id="d1e5a-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="d1e5a-117">Anropar Toffoli-simulatorn från kommando raden</span><span class="sxs-lookup"><span data-stu-id="d1e5a-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="d1e5a-118">När du kör ett Q# program från kommando raden använder du parametern **--simulatorn** (eller **-s** ) för att ange mål datorn för Toffoli Simulator.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="d1e5a-119">Följande kommando kör ett program med hjälp av resurs uppskattningen:</span><span class="sxs-lookup"><span data-stu-id="d1e5a-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="d1e5a-120">Anropar Toffoli-simulatorn från Juptyer Notebooks</span><span class="sxs-lookup"><span data-stu-id="d1e5a-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="d1e5a-121">Använd Q# kommandot Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) för att köra Q# åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="d1e5a-122">Åtgärder som stöds</span><span class="sxs-lookup"><span data-stu-id="d1e5a-122">Supported operations</span></span>

<span data-ttu-id="d1e5a-123">Toffoli Simulator stöder:</span><span class="sxs-lookup"><span data-stu-id="d1e5a-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="d1e5a-124">Rotationer och exponentiated Paulis, till exempel `R` och `Exp` , när den resulterande åtgärden är lika med `X` eller identitets mat ris.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="d1e5a-125">Mått och [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) -åtgärder, men endast i Pauli- `Z` basen.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="d1e5a-126">Observera att sannolikheten för en mått åtgärd alltid är **0** eller **1**; Det finns ingen slumpmässighet i Toffoli-simulatorn.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="d1e5a-127">`DumpMachine`och- `DumpRegister` funktioner.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="d1e5a-128">Båda funktionerna utvärderar aktuell `Z` bas status för varje qubit, en qubit per rad.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="d1e5a-129">Ange antalet qubits</span><span class="sxs-lookup"><span data-stu-id="d1e5a-129">Specifying the number of qubits</span></span>

<span data-ttu-id="d1e5a-130">Som standard `ToffoliSimulator` allokerar en instans utrymme för 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="d1e5a-131">Om algoritmen kräver mer qubits kan du ange antalet qubit genom att ange ett värde för `qubitCount` parametern för konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="d1e5a-132">För varje ytterligare qubit krävs bara en byte av minne, så det finns ingen betydande kostnad för att uppskatta antalet qubits som du behöver.</span><span class="sxs-lookup"><span data-stu-id="d1e5a-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="d1e5a-133">Exempel:</span><span class="sxs-lookup"><span data-stu-id="d1e5a-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="d1e5a-134">Se även</span><span class="sxs-lookup"><span data-stu-id="d1e5a-134">See also</span></span>

- [<span data-ttu-id="d1e5a-135">Uppskattning av Quantum-resurser</span><span class="sxs-lookup"><span data-stu-id="d1e5a-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="d1e5a-136">Quantum trace Simulator</span><span class="sxs-lookup"><span data-stu-id="d1e5a-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="d1e5a-137">Quantum, fullständig tillstånds Simulator</span><span class="sxs-lookup"><span data-stu-id="d1e5a-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 