---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847402"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="66b68-102">ControlledRotation-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="66b68-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="66b68-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="66b68-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="66b68-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="66b68-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="66b68-105">Beskriver en kontrollerad rotation i termer av mål-och kontroll index, rotations axel och index i en modell parameter vektor.</span><span class="sxs-lookup"><span data-stu-id="66b68-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="66b68-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="66b68-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="66b68-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66b68-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66b68-108">Index för mål-qubit för den här kontrollerade rotationen.</span><span class="sxs-lookup"><span data-stu-id="66b68-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="66b68-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="66b68-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="66b68-110">En matris med kontrollens qubit index för den här rotationen.</span><span class="sxs-lookup"><span data-stu-id="66b68-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="66b68-111">Axel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="66b68-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="66b68-112">Axeln för den här rotationen.</span><span class="sxs-lookup"><span data-stu-id="66b68-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="66b68-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66b68-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66b68-114">Ett index i en modell parameter vektor som beskriver vinkeln för den här rotationen.</span><span class="sxs-lookup"><span data-stu-id="66b68-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="66b68-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="66b68-115">Example</span></span>

<span data-ttu-id="66b68-116">Nedan visas en rotation om $X $-axeln för den första qubit i ett register, som styrs på den andra qubit och med en vinkel som angetts av den fjärde parametern i en sekventiell modell:</span><span class="sxs-lookup"><span data-stu-id="66b68-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="66b68-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="66b68-117">Remarks</span></span>

<span data-ttu-id="66b68-118">En okontrollerad rotation kan representeras genom `ControlIndices` att ställa in en tom matris med index `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="66b68-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>