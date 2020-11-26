---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194210"
---
# <a name="mresetx-operation"></a><span data-ttu-id="52ca1-102">MResetX-åtgärd</span><span class="sxs-lookup"><span data-stu-id="52ca1-102">MResetX operation</span></span>

<span data-ttu-id="52ca1-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="52ca1-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="52ca1-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="52ca1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="52ca1-105">Mäter en enskild qubit i X-basen och återställer den till ett fast initialt tillstånd efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="52ca1-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="52ca1-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="52ca1-106">Description</span></span>

<span data-ttu-id="52ca1-107">Utför en qubit-mätning i $X $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="52ca1-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="52ca1-108">Indata</span><span class="sxs-lookup"><span data-stu-id="52ca1-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="52ca1-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="52ca1-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="52ca1-110">En enda qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="52ca1-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="52ca1-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="52ca1-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="52ca1-112">Resultatet av att mäta `target` Pauli-$X $-basen.</span><span class="sxs-lookup"><span data-stu-id="52ca1-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>