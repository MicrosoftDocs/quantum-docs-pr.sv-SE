---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 59c0fa72c9ca8f3bc512b6ed674fd73babc57f84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202319"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="c3be1-102">AssertOperationsEqualReferenced-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c3be1-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="c3be1-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c3be1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c3be1-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c3be1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c3be1-105">Två åtgärder förutsätter att de fungerar identiskt för alla ingångs tillstånd.</span><span class="sxs-lookup"><span data-stu-id="c3be1-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="c3be1-106">Den här kontrollen implementeras med hjälp av Choi – Jamiołkowski-isomorphism för att minska försäkran till en qubit-tillstånds kontroll på två Entangled-register.</span><span class="sxs-lookup"><span data-stu-id="c3be1-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="c3be1-107">Den här åtgärden behöver därför bara ett enda anrop till varje åtgärd som testas, men kräver två gånger så många qubits som ska allokeras.</span><span class="sxs-lookup"><span data-stu-id="c3be1-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="c3be1-108">Denna kontroll kan användas för att se till att en optimerad version av en åtgärd fungerar identiskt med dess naïve-implementering, eller att en åtgärd som agerar på ett intervall av icke-Quantum-indata accepterar kända fall.</span><span class="sxs-lookup"><span data-stu-id="c3be1-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="c3be1-109">Indata</span><span class="sxs-lookup"><span data-stu-id="c3be1-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c3be1-110">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3be1-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3be1-111">Antalet qubits som ska skickas till varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c3be1-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="c3be1-112">faktiskt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3be1-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c3be1-113">Åtgärd som ska testas.</span><span class="sxs-lookup"><span data-stu-id="c3be1-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="c3be1-114">förväntat: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = just> [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3be1-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c3be1-115">Åtgärd som definierar det förväntade beteendet för åtgärden under test.</span><span class="sxs-lookup"><span data-stu-id="c3be1-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3be1-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3be1-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c3be1-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c3be1-117">Remarks</span></span>

<span data-ttu-id="c3be1-118">Den här åtgärden kräver att den förväntade åtgärden är adjointable, så att inversen kan utföras i själva mål registret.</span><span class="sxs-lookup"><span data-stu-id="c3be1-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="c3be1-119">Formellt, en kan ange en transponering-åtgärd, vilket innebär att detta krav uppfylls, men transponering-åtgärden är inte i allmänt fysiskt realizable för valfria Quantum-åtgärder och ingår därför inte här som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="c3be1-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>