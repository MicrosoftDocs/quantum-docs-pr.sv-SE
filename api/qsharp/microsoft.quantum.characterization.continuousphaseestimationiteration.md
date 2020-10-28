---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728233"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="da1ec-102">ContinuousPhaseEstimationIteration-åtgärd</span><span class="sxs-lookup"><span data-stu-id="da1ec-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="da1ec-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="da1ec-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="da1ec-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da1ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da1ec-105">Utför en enkel upprepning av en iterativ (klassisk) fas uppskattnings algoritm med godtyckliga verkliga befogenheter hos en enhetlig Oracle.</span><span class="sxs-lookup"><span data-stu-id="da1ec-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="da1ec-106">Indata</span><span class="sxs-lookup"><span data-stu-id="da1ec-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="da1ec-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="da1ec-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="da1ec-108">Åtgärder som utförs på en dubbel $t $ och ett register, t. ex. $U ^ t $ tillämpas på den aktuella registreringen, där $U $ är den kraft vars fas är att uppskatta, och där $t $ är den heltals effekt som ges till Oracle</span><span class="sxs-lookup"><span data-stu-id="da1ec-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="da1ec-109">tid: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="da1ec-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="da1ec-110">Antal gånger som den erhållna Oracle-gruppen ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="da1ec-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="da1ec-111">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="da1ec-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="da1ec-112">Vinkel för vilken du vill invertera fasen i kontrollen qubit innan du agerar på mål tillstånd.</span><span class="sxs-lookup"><span data-stu-id="da1ec-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="da1ec-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="da1ec-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="da1ec-114">Registrera dig för det tillstånd som har åtgärd ATS av den enhetliga Oracle.</span><span class="sxs-lookup"><span data-stu-id="da1ec-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="da1ec-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da1ec-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="da1ec-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da1ec-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

