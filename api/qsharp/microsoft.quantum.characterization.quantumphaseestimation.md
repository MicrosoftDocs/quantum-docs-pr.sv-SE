---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 14ba3e012f6561e7089f9fe59b2a13516b211d51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204223"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="5c164-102">QuantumPhaseEstimation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5c164-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="5c164-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="5c164-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="5c164-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c164-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c164-105">Utför en skattning av Quantum-fasen för en specifik Oracle `U` och `targetState` läser fasen till en big-endian-register.</span><span class="sxs-lookup"><span data-stu-id="5c164-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5c164-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5c164-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="5c164-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="5c164-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="5c164-108">En åtgärd som implementerar $U ^ m $ för angivet heltals-potenser m.</span><span class="sxs-lookup"><span data-stu-id="5c164-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="5c164-109">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5c164-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5c164-110">Ett Quantum-register som representerar det tillstånd $ \ket{\phi} $ som du har handlat om $U $.</span><span class="sxs-lookup"><span data-stu-id="5c164-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="5c164-111">Om $ \ket{\phi} $ är en eigenstate av $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ för $ \phi \in [0, 2 \ PI) $ en okänd fas.</span><span class="sxs-lookup"><span data-stu-id="5c164-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="5c164-112">controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="5c164-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="5c164-113">Ett heltals register med big-endian-representation som kan användas för att kontrol lera den angivna Oracle och som kommer att innehålla en representation av $ \phi $ efter den här åtgärdens användning.</span><span class="sxs-lookup"><span data-stu-id="5c164-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="5c164-114">ControlRegister antas starta i det ursprungliga läget $ \ket{00\cdots 0} $, där register längden anger önskad precision.</span><span class="sxs-lookup"><span data-stu-id="5c164-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c164-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c164-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

