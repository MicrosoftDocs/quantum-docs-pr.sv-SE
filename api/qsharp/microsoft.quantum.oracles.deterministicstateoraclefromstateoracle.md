---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: Funktionen DeterministicStateOracleFromStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854563"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="dea3f-102">Funktionen DeterministicStateOracleFromStateOracle</span><span class="sxs-lookup"><span data-stu-id="dea3f-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="dea3f-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="dea3f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="dea3f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dea3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dea3f-105">Konverterar en Oracle av typen `StateOracle` till `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="dea3f-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="dea3f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dea3f-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="dea3f-107">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dea3f-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dea3f-108">Indexet till flaggan qubit i `stateOracle` $A $, som uttryckligen agerar på två kassor: flaggan $f $ och system $s $, t. ex. $A \ket {0} \_ f\ket {\ PSI} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="dea3f-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="dea3f-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="dea3f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="dea3f-110">En tillstånds förberedelse Oracle-$A $ av typen `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="dea3f-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="dea3f-111">Utdata: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="dea3f-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="dea3f-112">Samma tillstånd som förbereder Oracle $A $, men nu av typ `DeterministicStateOracle` , så den agerar i ett register där $a, s $ inte längre uttryckligen separeras, t. ex.  $A \ket{0\psi} \_ {as} $.</span><span class="sxs-lookup"><span data-stu-id="dea3f-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="dea3f-113">Se även</span><span class="sxs-lookup"><span data-stu-id="dea3f-113">See Also</span></span>

- [<span data-ttu-id="dea3f-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="dea3f-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="dea3f-115">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="dea3f-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)