---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Funktionen StateOracleFromDeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842508"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="837e9-102">Funktionen StateOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="837e9-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="837e9-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="837e9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="837e9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="837e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="837e9-105">Konverterar en Oracle av typen `DeterministicStateOracle` till `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="837e9-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="837e9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="837e9-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="837e9-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="837e9-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="837e9-108">En tillstånds förberedelse Oracle-$A $ av typen `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="837e9-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="837e9-109">Utdata: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="837e9-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="837e9-110">Samma tillstånd som förbereder Oracle $A $, men nu av typen `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="837e9-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="837e9-111">Observera att flagg indexet i det här `StateOracle` är en dummy-variabel och har ingen påverkan.</span><span class="sxs-lookup"><span data-stu-id="837e9-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="837e9-112">Se även</span><span class="sxs-lookup"><span data-stu-id="837e9-112">See Also</span></span>

- [<span data-ttu-id="837e9-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="837e9-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="837e9-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="837e9-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)