---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853763"
---
# <a name="mresetx-operation"></a><span data-ttu-id="a55f7-102">MResetX-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a55f7-102">MResetX operation</span></span>

<span data-ttu-id="a55f7-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="a55f7-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="a55f7-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a55f7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a55f7-105">Mäter en enskild qubit i X-basen och återställer den till ett fast initialt tillstånd efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="a55f7-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="a55f7-106">Description</span><span class="sxs-lookup"><span data-stu-id="a55f7-106">Description</span></span>

<span data-ttu-id="a55f7-107">Utför en qubit-mätning i $X $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="a55f7-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="a55f7-108">Indata</span><span class="sxs-lookup"><span data-stu-id="a55f7-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="a55f7-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a55f7-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a55f7-110">En enda qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="a55f7-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a55f7-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="a55f7-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a55f7-112">Resultatet av att mäta `target` Pauli-$X $-basen.</span><span class="sxs-lookup"><span data-stu-id="a55f7-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>