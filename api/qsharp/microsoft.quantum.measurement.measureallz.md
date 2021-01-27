---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854677"
---
# <a name="measureallz-operation"></a><span data-ttu-id="e3a91-102">MeasureAllZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e3a91-102">MeasureAllZ operation</span></span>

<span data-ttu-id="e3a91-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e3a91-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e3a91-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3a91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3a91-105">I gemensamma fall åtgärdas ett register över qubits i Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="e3a91-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="e3a91-106">Description</span><span class="sxs-lookup"><span data-stu-id="e3a91-106">Description</span></span>

<span data-ttu-id="e3a91-107">Mäter ett register över qubits i $Z \otimes Z \otimes \cdots \otimes Z $, som representerar pariteten för hela registreringen.</span><span class="sxs-lookup"><span data-stu-id="e3a91-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="e3a91-108">Indata</span><span class="sxs-lookup"><span data-stu-id="e3a91-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="e3a91-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e3a91-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e3a91-110">Registret som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="e3a91-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e3a91-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="e3a91-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e3a91-112">Resultatet av mätningen $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="e3a91-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>