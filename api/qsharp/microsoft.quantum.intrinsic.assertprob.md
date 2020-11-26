---
uid: Microsoft.Quantum.Intrinsic.AssertProb
title: AssertProb-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: AssertProb
qsharp.summary: >-
  > [!WARNING]

  > AssertProb has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.
ms.openlocfilehash: 3c0f7c7a9e0190c5a8e5f3e70a5f82a8c23a97bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199106"
---
# <a name="assertprob-operation"></a><span data-ttu-id="e33f0-102">AssertProb-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e33f0-102">AssertProb operation</span></span>

<span data-ttu-id="e33f0-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e33f0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e33f0-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e33f0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="e33f0-105">AssertProb är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="e33f0-105">AssertProb has been deprecated.</span></span> <span data-ttu-id="e33f0-106">Använd <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> i stället.</span><span class="sxs-lookup"><span data-stu-id="e33f0-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.</span></span>



```qsharp
operation AssertProb (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e33f0-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e33f0-107">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="e33f0-108">Bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e33f0-108">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="e33f0-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e33f0-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="result--__invalidresult__"></a><span data-ttu-id="e33f0-110">resultat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="e33f0-110">result : __invalid<Result>__</span></span>




### <a name="prob--double"></a><span data-ttu-id="e33f0-111">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e33f0-111">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="msg--string"></a><span data-ttu-id="e33f0-112">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e33f0-112">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>




### <a name="tol--double"></a><span data-ttu-id="e33f0-113">TOL: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e33f0-113">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e33f0-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e33f0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

