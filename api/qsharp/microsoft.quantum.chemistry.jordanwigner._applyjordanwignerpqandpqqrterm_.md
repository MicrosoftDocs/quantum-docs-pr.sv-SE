---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQandPQQRTerm_
title: _ApplyJordanWignerPQandPQQRTerm_ -åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQandPQQRTerm_
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: a2a74ddeb7ecefaf4aa21374302d2709ee676e5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728110"
---
# <a name="_applyjordanwignerpqandpqqrterm_-operation"></a><span data-ttu-id="7e63f-102">_ApplyJordanWignerPQandPQQRTerm_ -åtgärd</span><span class="sxs-lookup"><span data-stu-id="7e63f-102">_ApplyJordanWignerPQandPQQRTerm_ operation</span></span>

<span data-ttu-id="7e63f-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7e63f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7e63f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e63f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e63f-105">Använder tid-utveckling med en PQ-eller PQQR-term som beskrivs av a `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="7e63f-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQandPQQRTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7e63f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7e63f-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="7e63f-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7e63f-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7e63f-108">`GeneratorIndex` representerar en PQ-eller PQQR-term.</span><span class="sxs-lookup"><span data-stu-id="7e63f-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="7e63f-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7e63f-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7e63f-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="7e63f-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7e63f-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7e63f-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7e63f-112">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="7e63f-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e63f-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e63f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

