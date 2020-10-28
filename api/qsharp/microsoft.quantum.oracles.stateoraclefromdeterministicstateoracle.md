---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Funktionen StateOracleFromDeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733342"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="01533-102">Funktionen StateOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="01533-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="01533-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="01533-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="01533-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01533-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01533-105">Konverterar en Oracle av typen `DeterministicStateOracle` till `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="01533-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="01533-106">Indata</span><span class="sxs-lookup"><span data-stu-id="01533-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="01533-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="01533-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="01533-108">En tillstånds förberedelse Oracle-$A $ av typen `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="01533-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="01533-109">Utdata: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="01533-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="01533-110">Samma tillstånd som förbereder Oracle $A $, men nu av typen `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="01533-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="01533-111">Observera att flagg indexet i det här `StateOracle` är en dummy-variabel och har ingen påverkan.</span><span class="sxs-lookup"><span data-stu-id="01533-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="01533-112">Se även</span><span class="sxs-lookup"><span data-stu-id="01533-112">See Also</span></span>

- [<span data-ttu-id="01533-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="01533-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="01533-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="01533-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)