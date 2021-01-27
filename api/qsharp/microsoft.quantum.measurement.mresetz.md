---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853745"
---
# <a name="mresetz-operation"></a><span data-ttu-id="8a431-102">MResetZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8a431-102">MResetZ operation</span></span>

<span data-ttu-id="8a431-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8a431-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8a431-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8a431-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8a431-105">Mäter en enskild qubit i Z-basen och återställer den till ett fast initialt tillstånd efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="8a431-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="8a431-106">Description</span><span class="sxs-lookup"><span data-stu-id="8a431-106">Description</span></span>

<span data-ttu-id="8a431-107">Utför en qubit-mätning i $Z $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.</span><span class="sxs-lookup"><span data-stu-id="8a431-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="8a431-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8a431-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="8a431-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8a431-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8a431-110">En enda qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="8a431-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8a431-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="8a431-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8a431-112">Resultatet av att mäta `target` Pauli-$Z $-basen.</span><span class="sxs-lookup"><span data-stu-id="8a431-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>