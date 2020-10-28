---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727087"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="e24fa-102">EncodeIntoBitFlipCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e24fa-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="e24fa-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e24fa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e24fa-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e24fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e24fa-105">Kodar till [3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-flip-kod.</span><span class="sxs-lookup"><span data-stu-id="e24fa-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="e24fa-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e24fa-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="e24fa-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e24fa-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e24fa-108">Ett register över fysiska qubits som representerar de data som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="e24fa-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="e24fa-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e24fa-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e24fa-110">Ett register över hjälp qubits inlednings vis i $ \ket {00} $ State som ska användas för att koda data som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="e24fa-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="e24fa-111">Utdata: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e24fa-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e24fa-112">De fysiska och tilläggs qubits som används i kodningen visas som ett logiskt register.</span><span class="sxs-lookup"><span data-stu-id="e24fa-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="e24fa-113">Se även</span><span class="sxs-lookup"><span data-stu-id="e24fa-113">See Also</span></span>

- [<span data-ttu-id="e24fa-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e24fa-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)