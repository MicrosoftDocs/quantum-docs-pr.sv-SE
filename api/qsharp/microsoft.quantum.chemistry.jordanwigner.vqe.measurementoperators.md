---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: Funktionen MeasurementOperators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727633"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="c6c05-102">Funktionen MeasurementOperators</span><span class="sxs-lookup"><span data-stu-id="c6c05-102">MeasurementOperators function</span></span>

<span data-ttu-id="c6c05-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="c6c05-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="c6c05-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6c05-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6c05-105">Beräknar alla mått operatörer som krävs för att beräkna förväntat en Jordan-Wigners period.</span><span class="sxs-lookup"><span data-stu-id="c6c05-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="c6c05-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c6c05-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c6c05-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6c05-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6c05-108">Antalet qubits som krävs för att simulera molekyl systemet.</span><span class="sxs-lookup"><span data-stu-id="c6c05-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="c6c05-109">index: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c6c05-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c6c05-110">En matris som innehåller index för qubit varje Pauli-operator tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="c6c05-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="c6c05-111">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6c05-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6c05-112">Jordan-Wigner termns typ.</span><span class="sxs-lookup"><span data-stu-id="c6c05-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="c6c05-113">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="c6c05-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="c6c05-114">En matris med mått operatorer (var och en är en matris med Pauli).</span><span class="sxs-lookup"><span data-stu-id="c6c05-114">An array of measurement operators (each being an array of Pauli).</span></span>