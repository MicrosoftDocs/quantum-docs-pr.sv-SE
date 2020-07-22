---
title: Fullständigt tillstånd Quantum Simulator – Quantum Development Kit
description: 'Lär dig hur du kör dina Q #-program i Microsoft Quantum Development Kit fullständig tillstånds Simulator.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871186"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="30ba9-103">Quantum Development Kit (QDK) fullständig tillstånds Simulator</span><span class="sxs-lookup"><span data-stu-id="30ba9-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="30ba9-104">QDK tillhandahåller en fullständig tillstånds simulator som simulerar en Quantum-dator på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="30ba9-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="30ba9-105">Du kan använda den fullständiga tillstånds simulatorn för att köra och felsöka Quantum-algoritmer skrivna i Q # och använda upp till 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="30ba9-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="30ba9-106">Den fullständiga tillstånds simulatorn liknar den Quantum simulator som används i [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) Platform från Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="30ba9-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="30ba9-107">Anropa och köra fullständig tillstånds Simulator</span><span class="sxs-lookup"><span data-stu-id="30ba9-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="30ba9-108">Du exponerar hela tillstånds simulatorn via- `QuantumSimulator` klassen.</span><span class="sxs-lookup"><span data-stu-id="30ba9-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="30ba9-109">Mer information finns i [sätt att köra ett Q #-program](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="30ba9-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="30ba9-110">Anropa simulatorn från C #</span><span class="sxs-lookup"><span data-stu-id="30ba9-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="30ba9-111">Skapa en instans av `QuantumSimulator` klassen och skicka den sedan till `Run` metoden för en Quantum-åtgärd, tillsammans med eventuella ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="30ba9-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="30ba9-112">Eftersom `QuantumSimulator` klassen implementerar <xref:System.IDisposable> gränssnittet måste du anropa `Dispose` metoden när du inte behöver instansen av simulatorn längre.</span><span class="sxs-lookup"><span data-stu-id="30ba9-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="30ba9-113">Det bästa sättet att göra detta är att omsluta Simulator deklarationen och åtgärderna i en [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) -instruktion som automatiskt anropar- `Dispose` metoden.</span><span class="sxs-lookup"><span data-stu-id="30ba9-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="30ba9-114">Anropa simulatorn från python</span><span class="sxs-lookup"><span data-stu-id="30ba9-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="30ba9-115">Använd metoden [simulera ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) från q # python-biblioteket med den importerade q #-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="30ba9-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="30ba9-116">Anropa simulatorn från kommando raden</span><span class="sxs-lookup"><span data-stu-id="30ba9-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="30ba9-117">När du kör ett Q #-program från kommando raden är den fullständiga tillstånds simulatorn standard mål datorn.</span><span class="sxs-lookup"><span data-stu-id="30ba9-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="30ba9-118">Alternativt kan du använda parametern **--Simulator** (eller **-s** genväg) för att ange önskad måldator.</span><span class="sxs-lookup"><span data-stu-id="30ba9-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="30ba9-119">Följande kommandon kör ett program med fullständig tillstånds Simulator.</span><span class="sxs-lookup"><span data-stu-id="30ba9-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="30ba9-120">Anropa simulatorn från Juptyer Notebooks</span><span class="sxs-lookup"><span data-stu-id="30ba9-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="30ba9-121">Använd SWEETIQ # Magic kommandot [% simulera](xref:microsoft.quantum.iqsharp.magic-ref.simulate) för att köra Q #-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="30ba9-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="30ba9-122">Dirigera simulatorn</span><span class="sxs-lookup"><span data-stu-id="30ba9-122">Seeding the simulator</span></span>

<span data-ttu-id="30ba9-123">Som standard använder den fullständiga tillstånds simulatorn en slump tals generator för att simulera Quantum-slumpmässig het.</span><span class="sxs-lookup"><span data-stu-id="30ba9-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="30ba9-124">I test syfte är det ibland användbart att ha deterministiska resultat.</span><span class="sxs-lookup"><span data-stu-id="30ba9-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="30ba9-125">I ett C#-program kan du göra detta genom att tillhandahålla ett start värde för slump tals generatorn i `QuantumSimulator` konstruktorn via `randomNumberGeneratorSeed` parametern.</span><span class="sxs-lookup"><span data-stu-id="30ba9-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="30ba9-126">Konfigurera trådar</span><span class="sxs-lookup"><span data-stu-id="30ba9-126">Configuring threads</span></span>

<span data-ttu-id="30ba9-127">Den fullständiga tillstånds simulatorn använder [OpenMP](http://www.openmp.org/) för att parallellisera de linjära algebra som krävs.</span><span class="sxs-lookup"><span data-stu-id="30ba9-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="30ba9-128">Som standard använder OpenMP alla tillgängliga maskin varu trådar, vilket innebär att program med små antal qubits ofta körs långsamt, eftersom den samordning som krävs för Dwarfs det faktiska arbetet.</span><span class="sxs-lookup"><span data-stu-id="30ba9-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="30ba9-129">Du kan åtgärda detta genom att ställa in miljövariabeln `OMP_NUM_THREADS` på ett litet nummer.</span><span class="sxs-lookup"><span data-stu-id="30ba9-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="30ba9-130">Som en regel för tummen konfigurerar du en tråd för upp till fyra qubits och sedan en ytterligare tråd per qubit.</span><span class="sxs-lookup"><span data-stu-id="30ba9-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="30ba9-131">Du kan behöva justera variabeln beroende på algoritmen.</span><span class="sxs-lookup"><span data-stu-id="30ba9-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="30ba9-132">Se även</span><span class="sxs-lookup"><span data-stu-id="30ba9-132">See also</span></span>

- [<span data-ttu-id="30ba9-133">Uppskattning av Quantum-resurser</span><span class="sxs-lookup"><span data-stu-id="30ba9-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="30ba9-134">Quantum Toffoli-Simulator</span><span class="sxs-lookup"><span data-stu-id="30ba9-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="30ba9-135">Quantum trace Simulator</span><span class="sxs-lookup"><span data-stu-id="30ba9-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)