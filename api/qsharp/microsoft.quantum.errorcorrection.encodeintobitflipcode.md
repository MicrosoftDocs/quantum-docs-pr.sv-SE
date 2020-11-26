---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b27759caba3c5dd363dbdf24d6e5de76870173cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200959"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="773f7-102">EncodeIntoBitFlipCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="773f7-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="773f7-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="773f7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="773f7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="773f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="773f7-105">Kodar till [3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-flip-kod.</span><span class="sxs-lookup"><span data-stu-id="773f7-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="773f7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="773f7-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="773f7-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="773f7-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="773f7-108">Ett register över fysiska qubits som representerar de data som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="773f7-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="773f7-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="773f7-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="773f7-110">Ett register över hjälp qubits inlednings vis i $ \ket {00} $ State som ska användas för att koda data som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="773f7-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="773f7-111">Utdata: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="773f7-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="773f7-112">De fysiska och tilläggs qubits som används i kodningen visas som ett logiskt register.</span><span class="sxs-lookup"><span data-stu-id="773f7-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="773f7-113">Se även</span><span class="sxs-lookup"><span data-stu-id="773f7-113">See Also</span></span>

- [<span data-ttu-id="773f7-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="773f7-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)