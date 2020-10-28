---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: _ApplyJordanWignerPQTerm_ -åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 8a9b41e17bcc46c5aff2b18455e1eac25620fe35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728104"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="282fd-102">_ApplyJordanWignerPQTerm_ -åtgärd</span><span class="sxs-lookup"><span data-stu-id="282fd-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="282fd-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="282fd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="282fd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="282fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="282fd-105">Använder tid-utveckling med en PQ-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="282fd-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="282fd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="282fd-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="282fd-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="282fd-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="282fd-108">`GeneratorIndex` representerar en PQ-term.</span><span class="sxs-lookup"><span data-stu-id="282fd-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="282fd-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="282fd-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="282fd-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="282fd-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="282fd-111">extraParityQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="282fd-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="282fd-112">Valfri paritets qubits som vänder dig till att ändra tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="282fd-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="282fd-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="282fd-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="282fd-114">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="282fd-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="282fd-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="282fd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

