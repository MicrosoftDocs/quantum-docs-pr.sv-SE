---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728230"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="dc6cb-102">DiscretePhaseEstimationIteration-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dc6cb-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="dc6cb-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="dc6cb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc6cb-105">Utför en enkel upprepning av en iterativ (klassisk) fas uppskattnings algoritm med hjälp av heltals befogenheter för en enhetlig Oracle.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="dc6cb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dc6cb-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="dc6cb-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="dc6cb-108">Åtgärder som utförs på ett heltal och ett register, t. ex. $U ^ m $ tillämpas på den aktuella registreringen, där $U $ är den kraft vars fas är att uppskatta, och där $m $ är den heltals effekt som ges till Oracle</span><span class="sxs-lookup"><span data-stu-id="dc6cb-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="dc6cb-109">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc6cb-110">Antal gånger som den erhållna Oracle-gruppen ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="dc6cb-111">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dc6cb-112">Vinkel för vilken du vill invertera fasen i kontrollen qubit innan du agerar på mål tillstånd.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="dc6cb-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc6cb-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc6cb-114">Registrera dig för det tillstånd som har åtgärd ATS av den enhetliga Oracle.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="dc6cb-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dc6cb-116">En hjälp qubit som används för att kontrol lera programmet för den specifika Oracle.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc6cb-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

