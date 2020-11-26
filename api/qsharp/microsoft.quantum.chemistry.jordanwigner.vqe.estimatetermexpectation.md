---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224657"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="7e512-102">EstimateTermExpectation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7e512-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="7e512-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="7e512-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="7e512-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7e512-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7e512-105">Beräknar den energi som är kopplad till en specifik Jordan-Wigner Hamiltonian-period</span><span class="sxs-lookup"><span data-stu-id="7e512-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="7e512-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e512-106">Description</span></span>

<span data-ttu-id="7e512-107">Den här åtgärden uppskattar förväntat värde som är kopplat till varje mått operator och multiplicerar det med motsvarande koefficient, med hjälp av sampling.</span><span class="sxs-lookup"><span data-stu-id="7e512-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="7e512-108">Resultaten sammanställs i en variabel som innehåller Jordan-Wigner periodens energi.</span><span class="sxs-lookup"><span data-stu-id="7e512-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="7e512-109">Indata</span><span class="sxs-lookup"><span data-stu-id="7e512-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="7e512-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="7e512-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7e512-111">Den plats som används för förberedelse av tillstånd.</span><span class="sxs-lookup"><span data-stu-id="7e512-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="7e512-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="7e512-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="7e512-113">Jordan-Wigner periodens mått operatorer.</span><span class="sxs-lookup"><span data-stu-id="7e512-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="7e512-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7e512-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7e512-115">Jordan-Wigner termns koefficienter.</span><span class="sxs-lookup"><span data-stu-id="7e512-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="7e512-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e512-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e512-117">Antalet qubits som krävs för att simulera molekyl systemet.</span><span class="sxs-lookup"><span data-stu-id="7e512-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="7e512-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e512-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e512-119">Antalet prover som ska användas för uppskattning av förväntad term.</span><span class="sxs-lookup"><span data-stu-id="7e512-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="7e512-120">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7e512-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7e512-121">Den energi som är kopplad till Jordan-Wigners perioden.</span><span class="sxs-lookup"><span data-stu-id="7e512-121">The energy associated to the Jordan-Wigner term.</span></span>