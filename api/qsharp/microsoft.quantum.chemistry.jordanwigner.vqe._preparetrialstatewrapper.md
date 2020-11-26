---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: 8e1a39cbd307a467ab7f0466c90722e1c8c46d4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224691"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="b19fb-102">_prepareTrialStateWrapper åtgärd</span><span class="sxs-lookup"><span data-stu-id="b19fb-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="b19fb-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="b19fb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="b19fb-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b19fb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b19fb-105">Privat omslutning runt PrepareTrialState för att göra det kompatibelt med EstimateFrequencyA genom att definiera ett intilliggande.</span><span class="sxs-lookup"><span data-stu-id="b19fb-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="b19fb-106">EstimateFrequencyA har inbyggd emulering som riktar sig mot QuantumSimulator, vilket påskyndar körningen.</span><span class="sxs-lookup"><span data-stu-id="b19fb-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b19fb-107">Indata</span><span class="sxs-lookup"><span data-stu-id="b19fb-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="b19fb-108">inputState: ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="b19fb-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="b19fb-109">Jordan-Wigner Indatatyp krävs för att PrepareTrialState ska kunna köras.</span><span class="sxs-lookup"><span data-stu-id="b19fb-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b19fb-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b19fb-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b19fb-111">Ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="b19fb-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b19fb-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b19fb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

