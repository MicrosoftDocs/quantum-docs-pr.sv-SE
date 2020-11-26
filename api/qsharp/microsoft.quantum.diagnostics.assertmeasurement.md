---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202455"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="49d8c-102">AssertMeasurement-åtgärd</span><span class="sxs-lookup"><span data-stu-id="49d8c-102">AssertMeasurement operation</span></span>

<span data-ttu-id="49d8c-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="49d8c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="49d8c-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="49d8c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="49d8c-105">Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-basen alltid har det aktuella resultatet.</span><span class="sxs-lookup"><span data-stu-id="49d8c-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="49d8c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="49d8c-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="49d8c-107">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="49d8c-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="49d8c-108">En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.</span><span class="sxs-lookup"><span data-stu-id="49d8c-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="49d8c-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="49d8c-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="49d8c-110">En register som ska göra försäkran.</span><span class="sxs-lookup"><span data-stu-id="49d8c-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="49d8c-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="49d8c-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="49d8c-112">Det förväntade resultatet av `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="49d8c-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="49d8c-113">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="49d8c-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="49d8c-114">Ett meddelande som ska rapporteras om kontrollen Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="49d8c-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49d8c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49d8c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="49d8c-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="49d8c-116">Remarks</span></span>

<span data-ttu-id="49d8c-117">Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="49d8c-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="49d8c-118">Se även</span><span class="sxs-lookup"><span data-stu-id="49d8c-118">See Also</span></span>

- [<span data-ttu-id="49d8c-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="49d8c-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)