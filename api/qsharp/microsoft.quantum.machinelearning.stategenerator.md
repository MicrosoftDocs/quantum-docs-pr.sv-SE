---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854876"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="fc865-102">StateGenerator-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="fc865-102">StateGenerator user defined type</span></span>

<span data-ttu-id="fc865-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fc865-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fc865-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fc865-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="fc865-105">Beskriver en åtgärd som förbereder en viss Indatatyp för en sekventiell klassificerare.</span><span class="sxs-lookup"><span data-stu-id="fc865-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="fc865-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="fc865-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="fc865-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc865-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc865-108">Antalet qubits som den kodade indatamängden är angiven på.</span><span class="sxs-lookup"><span data-stu-id="fc865-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="fc865-109">PREPARE: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="fc865-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fc865-110">En åtgärd som förbereder kodade indatatyper för en lite-endian-registrering av `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="fc865-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>