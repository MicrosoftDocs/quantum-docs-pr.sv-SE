---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 616174d4d7f5ac8f4cea9454098d819468076648
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727774"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="a2d87-102">JordanWignerFermionImpl-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a2d87-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="a2d87-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a2d87-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a2d87-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2d87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2d87-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JordanWigner-basen.</span><span class="sxs-lookup"><span data-stu-id="a2d87-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="a2d87-106">Mer information finns i [modeller för dynamisk Generator](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="a2d87-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a2d87-107">Indata</span><span class="sxs-lookup"><span data-stu-id="a2d87-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="a2d87-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a2d87-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a2d87-109">Ett Generator index som återges som en enhetlig utveckling i JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="a2d87-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="a2d87-110">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a2d87-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a2d87-111">En multiplikator vid tids åtgången för tids utveckling enligt den period som refereras i `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="a2d87-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a2d87-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2d87-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a2d87-113">Registrera dig efter tids utvecklings operatören.</span><span class="sxs-lookup"><span data-stu-id="a2d87-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2d87-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2d87-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

