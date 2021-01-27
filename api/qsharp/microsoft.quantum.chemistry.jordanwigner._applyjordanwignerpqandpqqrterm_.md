---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQandPQQRTerm_
title: _ApplyJordanWignerPQandPQQRTerm_ -åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQandPQQRTerm_
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: cd4a63378f4e491217a7bb478a8ea3dcce67bc5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839555"
---
# <a name="_applyjordanwignerpqandpqqrterm_-operation"></a><span data-ttu-id="5d7ad-102">_ApplyJordanWignerPQandPQQRTerm_ -åtgärd</span><span class="sxs-lookup"><span data-stu-id="5d7ad-102">_ApplyJordanWignerPQandPQQRTerm_ operation</span></span>

<span data-ttu-id="5d7ad-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5d7ad-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5d7ad-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5d7ad-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5d7ad-105">Använder tid-utveckling med en PQ-eller PQQR-term som beskrivs av a `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="5d7ad-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQandPQQRTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5d7ad-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5d7ad-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="5d7ad-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5d7ad-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5d7ad-108">`GeneratorIndex` representerar en PQ-eller PQQR-term.</span><span class="sxs-lookup"><span data-stu-id="5d7ad-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5d7ad-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d7ad-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d7ad-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="5d7ad-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5d7ad-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5d7ad-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5d7ad-112">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5d7ad-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d7ad-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d7ad-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

