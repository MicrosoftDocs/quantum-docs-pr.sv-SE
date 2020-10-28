---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726508"
---
# <a name="mresetz-operation"></a><span data-ttu-id="08c8d-102">MResetZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="08c8d-102">MResetZ operation</span></span>

<span data-ttu-id="08c8d-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="08c8d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="08c8d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08c8d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08c8d-105">Mäter en enskild qubit i Z-basen och återställer den till ett fast initialt tillstånd efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="08c8d-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="08c8d-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="08c8d-106">Description</span></span>

<span data-ttu-id="08c8d-107">Utför en qubit-mätning i $Z $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="08c8d-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="08c8d-108">Indata</span><span class="sxs-lookup"><span data-stu-id="08c8d-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="08c8d-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="08c8d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="08c8d-110">En enda qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="08c8d-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="08c8d-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="08c8d-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="08c8d-112">Resultatet av att mäta `target` Pauli-$Z $-basen.</span><span class="sxs-lookup"><span data-stu-id="08c8d-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>