---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 1448e760294e958b152f4ceb3faf979441ca986d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851856"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="8959a-102">EstimateRealOverlapBetweenStates-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8959a-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="8959a-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="8959a-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="8959a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8959a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8959a-105">Med två åtgärder som var och en förbereder kopior av ett tillstånd, beräknar den verkliga delen av överlappningen mellan de stater som förbereds av varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8959a-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="8959a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8959a-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="8959a-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="8959a-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8959a-108">En åtgärd som förbereder ett fast ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="8959a-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8959a-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="8959a-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8959a-110">Den första av de två tillstånds förberedelse åtgärderna som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="8959a-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8959a-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="8959a-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8959a-112">Den andra av de två tillstånds förberedelse åtgärderna som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="8959a-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="8959a-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8959a-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8959a-114">Antalet qubits som `commonPreparation` , `preparation1` och `preparation2` alla Act.</span><span class="sxs-lookup"><span data-stu-id="8959a-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="8959a-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8959a-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8959a-116">Antalet mätningar som ska användas vid uppskattning av överlappningen.</span><span class="sxs-lookup"><span data-stu-id="8959a-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="8959a-117">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8959a-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="8959a-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8959a-118">Remarks</span></span>

<span data-ttu-id="8959a-119">Den här åtgärden använder Hadamard-testet för att hitta den verkliga delen av $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ där $ \ket{\psi} $ är det tillstånd som förberetts av `commonPreparation` , $U $ är den enhetliga representationen av åtgärden `preparation1` och där $V $ motsvarar `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="8959a-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="8959a-120">Referenser</span><span class="sxs-lookup"><span data-stu-id="8959a-120">References</span></span>

- <span data-ttu-id="8959a-121">Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="8959a-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="8959a-122">Se även</span><span class="sxs-lookup"><span data-stu-id="8959a-122">See Also</span></span>

- [<span data-ttu-id="8959a-123">Microsoft. Quantum. karakterisering. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="8959a-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="8959a-124">Microsoft. Quantum. karakterisering. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="8959a-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)