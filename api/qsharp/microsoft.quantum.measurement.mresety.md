---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227037"
---
# <a name="mresety-operation"></a><span data-ttu-id="4ca45-102">MResetY-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4ca45-102">MResetY operation</span></span>

<span data-ttu-id="4ca45-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="4ca45-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="4ca45-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4ca45-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4ca45-105">Mäter en enskild qubit i Y-basen och återställer den till ett fast initialt tillstånd efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="4ca45-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="4ca45-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4ca45-106">Description</span></span>

<span data-ttu-id="4ca45-107">Utför en qubit-mätning i $Y $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="4ca45-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="4ca45-108">Indata</span><span class="sxs-lookup"><span data-stu-id="4ca45-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="4ca45-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4ca45-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4ca45-110">En enda qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="4ca45-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4ca45-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="4ca45-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="4ca45-112">Resultatet av att mäta `target` Pauli-$Y $-basen.</span><span class="sxs-lookup"><span data-stu-id="4ca45-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>