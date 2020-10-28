---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730987"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="dc0bc-102">MeasureWithScratch-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dc0bc-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="dc0bc-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="dc0bc-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="dc0bc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc0bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc0bc-105">Mäter den tilldelade Pauli-operatorn med hjälp av en explicit Scratch-qubit för att utföra mätningen.</span><span class="sxs-lookup"><span data-stu-id="dc0bc-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="dc0bc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dc0bc-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="dc0bc-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="dc0bc-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="dc0bc-108">En Pauli-operator med flera qubit anges som en matris med qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="dc0bc-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dc0bc-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc0bc-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc0bc-110">Qubit-register som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="dc0bc-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="dc0bc-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="dc0bc-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="dc0bc-112">Resultatet av att mäta den tilldelade Pauli-operatorn i `target` registret.</span><span class="sxs-lookup"><span data-stu-id="dc0bc-112">The result of measuring the given Pauli operator on the `target` register.</span></span>