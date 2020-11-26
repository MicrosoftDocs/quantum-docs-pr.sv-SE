---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202370"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="81feb-102">AssertMeasurementProbability-åtgärd</span><span class="sxs-lookup"><span data-stu-id="81feb-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="81feb-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="81feb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="81feb-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="81feb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="81feb-105">Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-grunden har det resultat som har givit den sannolikheten, inom viss tolerans.</span><span class="sxs-lookup"><span data-stu-id="81feb-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="81feb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="81feb-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="81feb-107">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="81feb-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="81feb-108">En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.</span><span class="sxs-lookup"><span data-stu-id="81feb-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="81feb-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81feb-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="81feb-110">En register som ska göra försäkran.</span><span class="sxs-lookup"><span data-stu-id="81feb-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="81feb-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="81feb-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="81feb-112">Ett förväntat resultat av `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="81feb-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="81feb-113">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81feb-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81feb-114">Sannolikheten med vilken det aktuella resultatet förväntas.</span><span class="sxs-lookup"><span data-stu-id="81feb-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="81feb-115">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="81feb-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="81feb-116">Ett meddelande som ska rapporteras om kontrollen Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="81feb-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="81feb-117">TOL: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81feb-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="81feb-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81feb-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="81feb-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="81feb-119">Remarks</span></span>

<span data-ttu-id="81feb-120">Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="81feb-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="81feb-121">Se även</span><span class="sxs-lookup"><span data-stu-id="81feb-121">See Also</span></span>

- [<span data-ttu-id="81feb-122">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="81feb-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)