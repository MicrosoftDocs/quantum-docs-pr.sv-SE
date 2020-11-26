---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e74c7fdc5acbb1a8c417bad3eb3630314e3f71bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201027"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="ad9aa-102">EncodeIntoSteaneCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ad9aa-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="ad9aa-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ad9aa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ad9aa-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad9aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad9aa-105">En kodnings åtgärd som mappar ett kodat Quantum-register till ett kodat Quantum-register under ⟦ 7, 1, 3 ⟧ Steane Quantum Code.</span><span class="sxs-lookup"><span data-stu-id="ad9aa-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="ad9aa-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ad9aa-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="ad9aa-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ad9aa-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ad9aa-108">Ett qubit-register som innehåller ett kodat Quantum-tillstånd</span><span class="sxs-lookup"><span data-stu-id="ad9aa-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="ad9aa-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ad9aa-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ad9aa-110">Ett qubit-register som ursprungligen är noll och som läggs till i Quantum-systemet så att en kodnings åtgärd kan utföras</span><span class="sxs-lookup"><span data-stu-id="ad9aa-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="ad9aa-111">Utdata: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="ad9aa-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="ad9aa-112">Ett Quantum-register som håller statusen efter att Steane-kodaren har tillämpats</span><span class="sxs-lookup"><span data-stu-id="ad9aa-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="ad9aa-113">Se även</span><span class="sxs-lookup"><span data-stu-id="ad9aa-113">See Also</span></span>

- [<span data-ttu-id="ad9aa-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ad9aa-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="ad9aa-115">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="ad9aa-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)