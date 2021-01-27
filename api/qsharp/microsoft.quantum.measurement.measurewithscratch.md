---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854664"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="547ba-102">MeasureWithScratch-åtgärd</span><span class="sxs-lookup"><span data-stu-id="547ba-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="547ba-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="547ba-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="547ba-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="547ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="547ba-105">Mäter den tilldelade Pauli-operatorn med hjälp av en explicit Scratch-qubit för att utföra mätningen.</span><span class="sxs-lookup"><span data-stu-id="547ba-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="547ba-106">Indata</span><span class="sxs-lookup"><span data-stu-id="547ba-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="547ba-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="547ba-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="547ba-108">En Pauli-operator med flera qubit anges som en matris med qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="547ba-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="547ba-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="547ba-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="547ba-110">Qubit-register som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="547ba-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="547ba-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="547ba-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="547ba-112">Resultatet av att mäta den tilldelade Pauli-operatorn i `target` registret.</span><span class="sxs-lookup"><span data-stu-id="547ba-112">The result of measuring the given Pauli operator on the `target` register.</span></span>