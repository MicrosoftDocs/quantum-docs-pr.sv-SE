---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208949"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="ca819-102">ApplyToEachIndexCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ca819-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="ca819-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca819-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca819-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca819-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca819-105">Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.</span><span class="sxs-lookup"><span data-stu-id="ca819-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="ca819-106">Modifieraren `CA` anger att en qubit-åtgärd är adjointable och kan kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="ca819-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ca819-107">Indata</span><span class="sxs-lookup"><span data-stu-id="ca819-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="ca819-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="ca819-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ca819-109">Åtgärd att tillämpa på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="ca819-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ca819-110">Registrera: ' ' []</span><span class="sxs-lookup"><span data-stu-id="ca819-110">register : 'T[]</span></span>

<span data-ttu-id="ca819-111">Matris för qubits som den aktuella åtgärden ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ca819-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca819-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca819-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca819-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ca819-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca819-114">Inte</span><span class="sxs-lookup"><span data-stu-id="ca819-114">'T</span></span>

<span data-ttu-id="ca819-115">Målet som varje åtgärd agerar på.</span><span class="sxs-lookup"><span data-stu-id="ca819-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca819-116">Se även</span><span class="sxs-lookup"><span data-stu-id="ca819-116">See Also</span></span>

- [<span data-ttu-id="ca819-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="ca819-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)