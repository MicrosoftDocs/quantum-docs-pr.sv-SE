---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851898"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="beff7-102">ContinuousPhaseEstimationIteration-åtgärd</span><span class="sxs-lookup"><span data-stu-id="beff7-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="beff7-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="beff7-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="beff7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="beff7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="beff7-105">Utför en enkel upprepning av en iterativ (klassisk) fas uppskattnings algoritm med godtyckliga verkliga befogenheter hos en enhetlig Oracle.</span><span class="sxs-lookup"><span data-stu-id="beff7-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="beff7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="beff7-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="beff7-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="beff7-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="beff7-108">Åtgärder som utförs på en dubbel $t $ och ett register, t. ex. $U ^ t $ tillämpas på den aktuella registreringen, där $U $ är den kraft vars fas är att uppskatta, och där $t $ är den heltals effekt som ges till Oracle</span><span class="sxs-lookup"><span data-stu-id="beff7-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="beff7-109">tid: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="beff7-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="beff7-110">Antal gånger som den erhållna Oracle-gruppen ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="beff7-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="beff7-111">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="beff7-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="beff7-112">Vinkel för vilken du vill invertera fasen i kontrollen qubit innan du agerar på mål tillstånd.</span><span class="sxs-lookup"><span data-stu-id="beff7-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="beff7-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="beff7-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="beff7-114">Registrera dig för det tillstånd som har åtgärd ATS av den enhetliga Oracle.</span><span class="sxs-lookup"><span data-stu-id="beff7-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="beff7-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="beff7-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="beff7-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="beff7-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

