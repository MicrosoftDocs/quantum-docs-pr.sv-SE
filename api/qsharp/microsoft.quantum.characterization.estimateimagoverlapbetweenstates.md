---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851871"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="89b11-102">EstimateImagOverlapBetweenStates-åtgärd</span><span class="sxs-lookup"><span data-stu-id="89b11-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="89b11-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="89b11-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="89b11-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89b11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89b11-105">Med två åtgärder som var och en förbereder kopior av ett tillstånd, beräknar den imaginära delen av överlappningen mellan de stadier som bearbetas av varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="89b11-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="89b11-106">Indata</span><span class="sxs-lookup"><span data-stu-id="89b11-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="89b11-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="89b11-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="89b11-108">En åtgärd som förbereder ett fast ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="89b11-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="89b11-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="89b11-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="89b11-110">Den första av de två tillstånds förberedelse åtgärderna som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="89b11-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="89b11-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="89b11-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="89b11-112">Den andra av de två tillstånds förberedelse åtgärderna som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="89b11-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="89b11-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89b11-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89b11-114">Antalet qubits som `commonPreparation` , `preparation1` och `preparation2` alla Act.</span><span class="sxs-lookup"><span data-stu-id="89b11-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="89b11-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89b11-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89b11-116">Antalet mätningar som ska användas vid uppskattning av överlappningen.</span><span class="sxs-lookup"><span data-stu-id="89b11-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="89b11-117">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89b11-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="89b11-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="89b11-118">Remarks</span></span>

<span data-ttu-id="89b11-119">Den här åtgärden använder Hadamard-testet för att hitta den imaginära delen av $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ där $ \ket{\psi} $ är det tillstånd som förberetts av `commonPreparation` , $U $ är den enhetliga representationen av åtgärden `preparation1` och där $V $ motsvarar `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="89b11-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="89b11-120">Referenser</span><span class="sxs-lookup"><span data-stu-id="89b11-120">References</span></span>

- <span data-ttu-id="89b11-121">Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="89b11-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="89b11-122">Se även</span><span class="sxs-lookup"><span data-stu-id="89b11-122">See Also</span></span>

- [<span data-ttu-id="89b11-123">Microsoft. Quantum. karakterisering. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="89b11-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="89b11-124">Microsoft. Quantum. karakterisering. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="89b11-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)