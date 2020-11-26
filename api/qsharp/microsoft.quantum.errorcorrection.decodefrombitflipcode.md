---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: DecodeFromBitFlipCode-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 84cf83f24d02f261f1768e16390f83c9b294b759
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201163"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="30a84-102">DecodeFromBitFlipCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="30a84-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="30a84-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="30a84-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="30a84-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30a84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30a84-105">Avkodar från [3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-flip-kod.</span><span class="sxs-lookup"><span data-stu-id="30a84-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="30a84-106">Indata</span><span class="sxs-lookup"><span data-stu-id="30a84-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="30a84-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="30a84-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="30a84-108">Ett kodblock med bit-flip-koden.</span><span class="sxs-lookup"><span data-stu-id="30a84-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="30a84-109">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="30a84-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="30a84-110">En tupel av de data som kodats i det logiska registret och den hjälp qubits som används för att representera syndrome.</span><span class="sxs-lookup"><span data-stu-id="30a84-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="30a84-111">Se även</span><span class="sxs-lookup"><span data-stu-id="30a84-111">See Also</span></span>

- [<span data-ttu-id="30a84-112">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="30a84-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="30a84-113">Microsoft. Quantum. ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="30a84-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)