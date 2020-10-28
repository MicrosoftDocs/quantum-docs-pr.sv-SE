---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: Funktionen ReflectionOracleFromDeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732179"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="631aa-102">Funktionen ReflectionOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="631aa-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="631aa-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="631aa-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="631aa-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="631aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="631aa-105">Skapar reflektion om ett angivet tillstånd från en Oracle.</span><span class="sxs-lookup"><span data-stu-id="631aa-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="631aa-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="631aa-106">Description</span></span>

<span data-ttu-id="631aa-107">Med tanke på den deterministiska tillstånds förberedelse Oracle som representeras av en enhetlig matris $O $, är resultatet av den här funktionen en Oracle som tillämpar en reflektion runt det tillstånd $ \ket{\psi} $ som förbereds av Oracle $O $; det vill säga status $ \ket{\psi} $ som $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="631aa-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="631aa-108">Indata</span><span class="sxs-lookup"><span data-stu-id="631aa-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="631aa-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="631aa-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="631aa-110">En Oracle som förbereder kopior av status $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="631aa-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="631aa-111">Utdata: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="631aa-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="631aa-112">En Oracle som visar om tillstånd $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="631aa-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="631aa-113">Se även</span><span class="sxs-lookup"><span data-stu-id="631aa-113">See Also</span></span>

- [<span data-ttu-id="631aa-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="631aa-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="631aa-115">Microsoft. Quantum. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="631aa-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)