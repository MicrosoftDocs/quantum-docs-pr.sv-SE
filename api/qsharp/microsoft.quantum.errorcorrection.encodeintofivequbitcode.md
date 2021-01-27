---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826326"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="90be9-102">EncodeIntoFiveQubitCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="90be9-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="90be9-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="90be9-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="90be9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90be9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90be9-105">Kodar till ⟦ 5, 1, 3 ⟧, Quantum-koden.</span><span class="sxs-lookup"><span data-stu-id="90be9-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="90be9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="90be9-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="90be9-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="90be9-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="90be9-108">En qubit som representerar ett kodat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="90be9-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="90be9-109">Matrisen `Qubit[]` har längden 1.</span><span class="sxs-lookup"><span data-stu-id="90be9-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="90be9-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="90be9-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="90be9-111">Ett register över hjälp-qubits som ska användas för att representera kodat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="90be9-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="90be9-112">Utdata: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="90be9-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="90be9-113">En matris med fysiska qubits av typen `LogicalRegister` som lagrar det kodade läget.</span><span class="sxs-lookup"><span data-stu-id="90be9-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="90be9-114">Se även</span><span class="sxs-lookup"><span data-stu-id="90be9-114">See Also</span></span>

- [<span data-ttu-id="90be9-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="90be9-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)