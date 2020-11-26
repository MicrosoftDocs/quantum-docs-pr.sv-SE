---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211567"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="c50a4-102">StateGenerator-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="c50a4-102">StateGenerator user defined type</span></span>

<span data-ttu-id="c50a4-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c50a4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c50a4-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c50a4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c50a4-105">Beskriver en åtgärd som förbereder en viss Indatatyp för en sekventiell klassificerare.</span><span class="sxs-lookup"><span data-stu-id="c50a4-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="c50a4-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="c50a4-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c50a4-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c50a4-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c50a4-108">Antalet qubits som den kodade indatamängden är angiven på.</span><span class="sxs-lookup"><span data-stu-id="c50a4-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="c50a4-109">PREPARE: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="c50a4-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c50a4-110">En åtgärd som förbereder kodade indatatyper för en lite-endian-registrering av `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="c50a4-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>