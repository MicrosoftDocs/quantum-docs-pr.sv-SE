---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727084"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="08fe3-102">EncodeIntoFiveQubitCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="08fe3-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="08fe3-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="08fe3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="08fe3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08fe3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08fe3-105">Kodar till ⟦ 5, 1, 3 ⟧, Quantum-koden.</span><span class="sxs-lookup"><span data-stu-id="08fe3-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="08fe3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="08fe3-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="08fe3-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="08fe3-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="08fe3-108">En qubit som representerar ett kodat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="08fe3-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="08fe3-109">Matrisen `Qubit[]` har längden 1.</span><span class="sxs-lookup"><span data-stu-id="08fe3-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="08fe3-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="08fe3-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="08fe3-111">Ett register över hjälp-qubits som ska användas för att representera kodat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="08fe3-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="08fe3-112">Utdata: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="08fe3-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="08fe3-113">En matris med fysiska qubits av typen `LogicalRegister` som lagrar det kodade läget.</span><span class="sxs-lookup"><span data-stu-id="08fe3-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="08fe3-114">Se även</span><span class="sxs-lookup"><span data-stu-id="08fe3-114">See Also</span></span>

- [<span data-ttu-id="08fe3-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="08fe3-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)