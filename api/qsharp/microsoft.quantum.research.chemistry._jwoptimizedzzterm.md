---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: _JWOptimizedZZTerm åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732518"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="54cb1-102">_JWOptimizedZZTerm åtgärd</span><span class="sxs-lookup"><span data-stu-id="54cb1-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="54cb1-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="54cb1-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="54cb1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54cb1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54cb1-105">Använder tid-utveckling med en ZZ-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="54cb1-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="54cb1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="54cb1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="54cb1-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="54cb1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="54cb1-108">`GeneratorIndex` representerar en ZZ-term.</span><span class="sxs-lookup"><span data-stu-id="54cb1-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="54cb1-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="54cb1-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="54cb1-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="54cb1-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="54cb1-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="54cb1-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="54cb1-112">Qubit som avgör tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="54cb1-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="54cb1-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="54cb1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="54cb1-114">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="54cb1-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54cb1-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54cb1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
