---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Funktionen StateOracleFromDeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193819"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="afb0c-102">Funktionen StateOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="afb0c-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="afb0c-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="afb0c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="afb0c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afb0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afb0c-105">Konverterar en Oracle av typen `DeterministicStateOracle` till `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="afb0c-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="afb0c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="afb0c-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="afb0c-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="afb0c-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="afb0c-108">En tillstånds förberedelse Oracle-$A $ av typen `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="afb0c-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="afb0c-109">Utdata: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="afb0c-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="afb0c-110">Samma tillstånd som förbereder Oracle $A $, men nu av typen `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="afb0c-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="afb0c-111">Observera att flagg indexet i det här `StateOracle` är en dummy-variabel och har ingen påverkan.</span><span class="sxs-lookup"><span data-stu-id="afb0c-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="afb0c-112">Se även</span><span class="sxs-lookup"><span data-stu-id="afb0c-112">See Also</span></span>

- [<span data-ttu-id="afb0c-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="afb0c-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="afb0c-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="afb0c-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)