---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732302"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="d4e23-102">StateGenerator-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d4e23-102">StateGenerator user defined type</span></span>

<span data-ttu-id="d4e23-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d4e23-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d4e23-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4e23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4e23-105">Beskriver en åtgärd som förbereder en viss Indatatyp för en sekventiell klassificerare.</span><span class="sxs-lookup"><span data-stu-id="d4e23-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="d4e23-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="d4e23-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d4e23-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4e23-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4e23-108">Antalet qubits som den kodade indatamängden är angiven på.</span><span class="sxs-lookup"><span data-stu-id="d4e23-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="d4e23-109">Förbereda: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="d4e23-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d4e23-110">En åtgärd som förbereder kodade indatatyper för en lite-endian-registrering av `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="d4e23-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>