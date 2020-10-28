---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727333"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="0354a-102">AssertMeasurementProbability-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0354a-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="0354a-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0354a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0354a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0354a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0354a-105">Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-grunden har det resultat som har givit den sannolikheten, inom viss tolerans.</span><span class="sxs-lookup"><span data-stu-id="0354a-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="0354a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0354a-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="0354a-107">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="0354a-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="0354a-108">En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.</span><span class="sxs-lookup"><span data-stu-id="0354a-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0354a-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0354a-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0354a-110">En register som ska göra försäkran.</span><span class="sxs-lookup"><span data-stu-id="0354a-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="0354a-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="0354a-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="0354a-112">Ett förväntat resultat av `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="0354a-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="0354a-113">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0354a-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0354a-114">Sannolikheten med vilken det aktuella resultatet förväntas.</span><span class="sxs-lookup"><span data-stu-id="0354a-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="0354a-115">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0354a-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0354a-116">Ett meddelande som ska rapporteras om kontrollen Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="0354a-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="0354a-117">TOL: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0354a-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="0354a-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0354a-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0354a-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0354a-119">Remarks</span></span>

<span data-ttu-id="0354a-120">Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0354a-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0354a-121">Se även</span><span class="sxs-lookup"><span data-stu-id="0354a-121">See Also</span></span>

- [<span data-ttu-id="0354a-122">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="0354a-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)