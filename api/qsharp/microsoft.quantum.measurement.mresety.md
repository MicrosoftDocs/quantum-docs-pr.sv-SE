---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733795"
---
# <a name="mresety-operation"></a><span data-ttu-id="2ac9d-102">MResetY-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ac9d-102">MResetY operation</span></span>

<span data-ttu-id="2ac9d-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2ac9d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2ac9d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ac9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ac9d-105">Mäter en enskild qubit i Y-basen och återställer den till ett fast initialt tillstånd efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="2ac9d-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="2ac9d-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2ac9d-106">Description</span></span>

<span data-ttu-id="2ac9d-107">Utför en qubit-mätning i $Y $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="2ac9d-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="2ac9d-108">Indata</span><span class="sxs-lookup"><span data-stu-id="2ac9d-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2ac9d-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2ac9d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2ac9d-110">En enda qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="2ac9d-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2ac9d-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="2ac9d-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2ac9d-112">Resultatet av att mäta `target` Pauli-$Y $-basen.</span><span class="sxs-lookup"><span data-stu-id="2ac9d-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>