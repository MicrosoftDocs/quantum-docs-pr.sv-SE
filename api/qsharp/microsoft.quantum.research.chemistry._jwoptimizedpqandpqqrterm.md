---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 97ae285ede38883f058b3e7609f9a26fb9e4340a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854782"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="437da-102">_JWOptimizedPQandPQQRTerm åtgärd</span><span class="sxs-lookup"><span data-stu-id="437da-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="437da-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="437da-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="437da-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="437da-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="437da-105">Använder tid-utveckling med en PQ-eller PQQR-term som beskrivs av a `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="437da-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="437da-106">Indata</span><span class="sxs-lookup"><span data-stu-id="437da-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="437da-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="437da-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="437da-108">`GeneratorIndex` representerar en PQ-eller PQQr-term.</span><span class="sxs-lookup"><span data-stu-id="437da-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="437da-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="437da-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="437da-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="437da-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="437da-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="437da-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="437da-112">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="437da-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="437da-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="437da-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="437da-114">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="437da-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="437da-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="437da-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

