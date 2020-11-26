---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 70e52b7440dca1fa8761db13d6187cb6bf8c43c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200993"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="ab661-102">EncodeIntoFiveQubitCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ab661-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="ab661-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ab661-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ab661-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab661-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab661-105">Kodar till ⟦ 5, 1, 3 ⟧, Quantum-koden.</span><span class="sxs-lookup"><span data-stu-id="ab661-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="ab661-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ab661-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="ab661-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ab661-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ab661-108">En qubit som representerar ett kodat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="ab661-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="ab661-109">Matrisen `Qubit[]` har längden 1.</span><span class="sxs-lookup"><span data-stu-id="ab661-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="ab661-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ab661-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ab661-111">Ett register över hjälp-qubits som ska användas för att representera kodat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="ab661-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="ab661-112">Utdata: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="ab661-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="ab661-113">En matris med fysiska qubits av typen `LogicalRegister` som lagrar det kodade läget.</span><span class="sxs-lookup"><span data-stu-id="ab661-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab661-114">Se även</span><span class="sxs-lookup"><span data-stu-id="ab661-114">See Also</span></span>

- [<span data-ttu-id="ab661-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ab661-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)