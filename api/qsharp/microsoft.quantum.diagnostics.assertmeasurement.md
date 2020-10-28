---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727357"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="69f31-102">AssertMeasurement-åtgärd</span><span class="sxs-lookup"><span data-stu-id="69f31-102">AssertMeasurement operation</span></span>

<span data-ttu-id="69f31-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="69f31-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="69f31-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69f31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69f31-105">Förutsätter att mätningen av den aktuella qubits i den aktuella Pauli-basen alltid har det aktuella resultatet.</span><span class="sxs-lookup"><span data-stu-id="69f31-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="69f31-106">Indata</span><span class="sxs-lookup"><span data-stu-id="69f31-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="69f31-107">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="69f31-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="69f31-108">En mätnings funktion som försäkrar sannolikheten för, uttryckt som en Pauli-operatör med flera qubit.</span><span class="sxs-lookup"><span data-stu-id="69f31-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="69f31-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69f31-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69f31-110">En register som ska göra försäkran.</span><span class="sxs-lookup"><span data-stu-id="69f31-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="69f31-111">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="69f31-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="69f31-112">Det förväntade resultatet av `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="69f31-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="69f31-113">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="69f31-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="69f31-114">Ett meddelande som ska rapporteras om kontrollen Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="69f31-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69f31-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69f31-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="69f31-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="69f31-116">Remarks</span></span>

<span data-ttu-id="69f31-117">Observera att det inte går att kontrol lera villkoret i intilliggande och kontrollerade versioner av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="69f31-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="69f31-118">Se även</span><span class="sxs-lookup"><span data-stu-id="69f31-118">See Also</span></span>

- [<span data-ttu-id="69f31-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="69f31-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)