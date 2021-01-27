---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: d154f9f1f674dc7cf7af9807922b0897540087b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857959"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="eb035-102">AdiabaticStateEnergyUnitary-åtgärd</span><span class="sxs-lookup"><span data-stu-id="eb035-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="eb035-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="eb035-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="eb035-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb035-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb035-105">Utför tillstånds förberedelse genom att använda en `statePrepUnitary` på ingångs läget, följt av adiabatic-tillstånds förberedelse med hjälp av en `adiabaticUnitary` , och slutligen en uppskattning av fasen med avseende `qpeUnitary` på det resulterande läget med hjälp av en `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="eb035-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="eb035-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eb035-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="eb035-107">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb035-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb035-108">En Oracle som representerar tillstånds förberedelse för den inledande dynamiska generatorn.</span><span class="sxs-lookup"><span data-stu-id="eb035-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="eb035-109">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb035-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb035-110">En Oracle som representerar algoritmen för adiabatic-utveckling som används för att implementera svepen till det slutliga tillståndets slut.</span><span class="sxs-lookup"><span data-stu-id="eb035-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="eb035-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="eb035-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="eb035-112">En Oracle som representerar en enhetlig operatör $U $ som representerar utvecklingen för tid $ \delta t $ under en dynamisk Generator med jord tillstånd $ \ket{\phi} $ och mark State Energy $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="eb035-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="eb035-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb035-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="eb035-114">En åtgärd som utför en fas uppskattning för en bestämd åtgärd.</span><span class="sxs-lookup"><span data-stu-id="eb035-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="eb035-115">Se [uppskattning av iterativa faser](/quantum/libraries/characterization#iterative-phase-estimation) för mer information.</span><span class="sxs-lookup"><span data-stu-id="eb035-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="eb035-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb035-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb035-117">Ett register över qubits som ska användas för att utföra simuleringen.</span><span class="sxs-lookup"><span data-stu-id="eb035-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="eb035-118">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb035-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb035-119">En uppskattning av $ \hat{\phi} $ av mark State Energy $ \phi $ av generatorn som representeras av $U $.</span><span class="sxs-lookup"><span data-stu-id="eb035-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>