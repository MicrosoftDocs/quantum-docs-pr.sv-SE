---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830824"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="ab9b2-102">AssertMeasurementProbability-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ab9b2-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="ab9b2-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ab9b2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ab9b2-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ab9b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ab9b2-105">Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-grunden har det resultat som har givit den sannolikheten, inom viss tolerans.</span><span class="sxs-lookup"><span data-stu-id="ab9b2-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ab9b2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ab9b2-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="ab9b2-107">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ab9b2-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ab9b2-108">En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.</span><span class="sxs-lookup"><span data-stu-id="ab9b2-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ab9b2-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ab9b2-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ab9b2-110">En register som ska göra försäkran.</span><span class="sxs-lookup"><span data-stu-id="ab9b2-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="ab9b2-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="ab9b2-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="ab9b2-112">Ett förväntat resultat av `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="ab9b2-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="ab9b2-113">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab9b2-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab9b2-114">Sannolikheten med vilken det aktuella resultatet förväntas.</span><span class="sxs-lookup"><span data-stu-id="ab9b2-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="ab9b2-115">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ab9b2-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ab9b2-116">Ett meddelande som ska rapporteras om kontrollen Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="ab9b2-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="ab9b2-117">TOL: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab9b2-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ab9b2-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab9b2-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ab9b2-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="ab9b2-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="ab9b2-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ab9b2-120">Remarks</span></span>

<span data-ttu-id="ab9b2-121">Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="ab9b2-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab9b2-122">Se även</span><span class="sxs-lookup"><span data-stu-id="ab9b2-122">See Also</span></span>

- [<span data-ttu-id="ab9b2-123">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="ab9b2-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)