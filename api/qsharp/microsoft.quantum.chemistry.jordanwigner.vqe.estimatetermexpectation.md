---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727654"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="90288-102">EstimateTermExpectation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="90288-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="90288-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="90288-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="90288-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90288-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90288-105">Beräknar den energi som är kopplad till en specifik Jordan-Wigner Hamiltonian-period</span><span class="sxs-lookup"><span data-stu-id="90288-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="90288-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="90288-106">Description</span></span>

<span data-ttu-id="90288-107">Den här åtgärden uppskattar förväntat värde som är kopplat till varje mått operator och multiplicerar det med motsvarande koefficient, med hjälp av sampling.</span><span class="sxs-lookup"><span data-stu-id="90288-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="90288-108">Resultaten sammanställs i en variabel som innehåller Jordan-Wigner periodens energi.</span><span class="sxs-lookup"><span data-stu-id="90288-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="90288-109">Indata</span><span class="sxs-lookup"><span data-stu-id="90288-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="90288-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="90288-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="90288-111">Den plats som används för förberedelse av tillstånd.</span><span class="sxs-lookup"><span data-stu-id="90288-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="90288-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="90288-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="90288-113">Jordan-Wigner periodens mått operatorer.</span><span class="sxs-lookup"><span data-stu-id="90288-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="90288-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="90288-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="90288-115">Jordan-Wigner termns koefficienter.</span><span class="sxs-lookup"><span data-stu-id="90288-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="90288-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90288-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90288-117">Antalet qubits som krävs för att simulera molekyl systemet.</span><span class="sxs-lookup"><span data-stu-id="90288-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="90288-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90288-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90288-119">Antalet prover som ska användas för uppskattning av förväntad term.</span><span class="sxs-lookup"><span data-stu-id="90288-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="90288-120">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90288-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90288-121">Den energi som är kopplad till Jordan-Wigners perioden.</span><span class="sxs-lookup"><span data-stu-id="90288-121">The energy associated to the Jordan-Wigner term.</span></span>