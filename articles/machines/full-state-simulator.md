---
title: Quantum Development Kit full State Simulator | Microsoft Docs
description: Översikt över Microsofts Quantum Development Kit full State Simulator
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184686"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="01797-103">Quantum Development Kit full State Simulator</span><span class="sxs-lookup"><span data-stu-id="01797-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="01797-104">Quantum Development Kit innehåller en fullständigt tillstånd Quantum simulator som liknar [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) från Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="01797-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="01797-105">Den här simulatorn kan användas för att köra och felsöka Quantum-algoritmer skrivna i Q # på din dator.</span><span class="sxs-lookup"><span data-stu-id="01797-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="01797-106">Den här Quantum simulatorn exponeras via `QuantumSimulator`-klassen.</span><span class="sxs-lookup"><span data-stu-id="01797-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="01797-107">Om du vill använda simulatorn skapar du bara en instans av den här klassen och skickar den till `Run`-metoden för den Quantum-åtgärd som du vill köra tillsammans med resten av parametrarna:</span><span class="sxs-lookup"><span data-stu-id="01797-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="01797-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="01797-108">IDisposable</span></span>

<span data-ttu-id="01797-109">`QuantumSimulator`-klassen implementerar <xref:System.IDisposable>, så `Dispose`-metoden ska anropas när instansen av simulatorn inte används längre.</span><span class="sxs-lookup"><span data-stu-id="01797-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="01797-110">Det bästa sättet att göra detta är att omsluta simulatorn i en `using`-instruktion, som i exemplet ovan.</span><span class="sxs-lookup"><span data-stu-id="01797-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="01797-111">Dirigeringsrouter</span><span class="sxs-lookup"><span data-stu-id="01797-111">Seed</span></span>

<span data-ttu-id="01797-112">`QuantumSimulator` använder en slump tals generator för att simulera Quantum-slumpmässig het.</span><span class="sxs-lookup"><span data-stu-id="01797-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="01797-113">I test syfte är det ibland användbart att ha deterministiska resultat.</span><span class="sxs-lookup"><span data-stu-id="01797-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="01797-114">Detta kan åstadkommas genom att tillhandahålla ett start värde för slump tals generatorn i `QuantumSimulator`s konstruktorn via `randomNumberGeneratorSeed` parameter:</span><span class="sxs-lookup"><span data-stu-id="01797-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="01797-115">Konversation</span><span class="sxs-lookup"><span data-stu-id="01797-115">Threads</span></span>

<span data-ttu-id="01797-116">`QuantumSimulator` använder [OpenMP](http://www.openmp.org/) för att parallellisera de linjära algebra som krävs.</span><span class="sxs-lookup"><span data-stu-id="01797-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="01797-117">Som standard använder OpenMP alla tillgängliga maskin varu trådar, vilket innebär att program med små mängder qubits ofta kommer att köras långsamt, eftersom den samordning som krävs kommer att Dwarf det faktiska arbetet.</span><span class="sxs-lookup"><span data-stu-id="01797-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="01797-118">Detta kan åtgärdas genom att ställa in miljövariabeln `OMP_NUM_THREADS` till ett litet tal.</span><span class="sxs-lookup"><span data-stu-id="01797-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="01797-119">En mycket bra tumregel är att 1 tråd är bra för upp till ungefär 4 qubits och en ytterligare tråd per qubit är bra, även om det är mycket beroende av algoritmen.</span><span class="sxs-lookup"><span data-stu-id="01797-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

