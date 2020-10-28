---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728197"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="5dc9d-102">EstimateOverlapBetweenStates-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5dc9d-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="5dc9d-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="5dc9d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="5dc9d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dc9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dc9d-105">Med två åtgärder som varje förbereder kopior av ett tillstånd, beräknar kvadraten överlappningen mellan de stater som för beretts av varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="5dc9d-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="5dc9d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5dc9d-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="5dc9d-107">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="5dc9d-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5dc9d-108">Den första av de två tillstånds förberedelse åtgärderna som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="5dc9d-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="5dc9d-109">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="5dc9d-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5dc9d-110">Den andra av de två tillstånds förberedelse åtgärderna som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="5dc9d-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="5dc9d-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dc9d-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dc9d-112">Antalet qubits som `commonPreparation` , `preparation1` och `preparation2` alla Act.</span><span class="sxs-lookup"><span data-stu-id="5dc9d-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="5dc9d-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dc9d-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dc9d-114">Antalet mätningar som ska användas vid uppskattning av överlappningen.</span><span class="sxs-lookup"><span data-stu-id="5dc9d-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="5dc9d-115">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5dc9d-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="5dc9d-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5dc9d-116">Remarks</span></span>

<span data-ttu-id="5dc9d-117">Den här åtgärden använder SWAP-testet för att hitta $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $ där $U $ är en enhetlig representation av åtgärden `preparation1` och där $V $ motsvarar `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="5dc9d-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dc9d-118">Se även</span><span class="sxs-lookup"><span data-stu-id="5dc9d-118">See Also</span></span>

- [<span data-ttu-id="5dc9d-119">Microsoft. Quantum. karakterisering. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="5dc9d-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="5dc9d-120">Microsoft. Quantum. karakterisering. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="5dc9d-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)