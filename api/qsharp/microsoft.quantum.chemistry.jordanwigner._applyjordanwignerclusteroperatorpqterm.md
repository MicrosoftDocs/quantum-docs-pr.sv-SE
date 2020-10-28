---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: _ApplyJordanWignerClusterOperatorPQTerm åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: d72ddea439c45936caefa74add4a0444afe4318e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728119"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="df67a-102">_ApplyJordanWignerClusterOperatorPQTerm åtgärd</span><span class="sxs-lookup"><span data-stu-id="df67a-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="df67a-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="df67a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="df67a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df67a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df67a-105">Använder tid-utveckling av en kluster operatörs PQ term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="df67a-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="df67a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="df67a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="df67a-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="df67a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="df67a-108">`GeneratorIndex` representerar en PQ term för kluster operatorn.</span><span class="sxs-lookup"><span data-stu-id="df67a-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="df67a-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df67a-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df67a-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="df67a-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="df67a-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df67a-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df67a-112">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="df67a-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df67a-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df67a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

