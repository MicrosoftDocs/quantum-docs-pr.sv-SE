---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194159"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="39c99-102">SetToBasisState-åtgärd</span><span class="sxs-lookup"><span data-stu-id="39c99-102">SetToBasisState operation</span></span>

<span data-ttu-id="39c99-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="39c99-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="39c99-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="39c99-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="39c99-105">Ställer in en qubit till ett angivet beräknings underlag genom att mäta qubit och tillämpa en bit-flip vid behov.</span><span class="sxs-lookup"><span data-stu-id="39c99-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="39c99-106">Indata</span><span class="sxs-lookup"><span data-stu-id="39c99-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="39c99-107">önskad: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="39c99-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="39c99-108">Det bas tillstånd som qubit ska vara inställt på.</span><span class="sxs-lookup"><span data-stu-id="39c99-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="39c99-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="39c99-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="39c99-110">Qubit vars tillstånd ska anges.</span><span class="sxs-lookup"><span data-stu-id="39c99-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39c99-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39c99-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39c99-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="39c99-112">Remarks</span></span>

<span data-ttu-id="39c99-113">Som en invariant av den här åtgärden, anropas `M(q)` omedelbart efter `SetToBasisState(result, q)` att det returneras `result` .</span><span class="sxs-lookup"><span data-stu-id="39c99-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>