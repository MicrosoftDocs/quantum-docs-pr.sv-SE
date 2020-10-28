---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: _ApplyJordanWigner0123Term_ -åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 36590b2ee9f6f6c2b5e076f8e334dfe7b0144e5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728122"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="1e958-102">_ApplyJordanWigner0123Term_ -åtgärd</span><span class="sxs-lookup"><span data-stu-id="1e958-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="1e958-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1e958-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1e958-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e958-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e958-105">Använder tid-utveckling med en PQRS-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="1e958-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1e958-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1e958-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="1e958-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1e958-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1e958-108">`GeneratorIndex` representerar en PQRS-term.</span><span class="sxs-lookup"><span data-stu-id="1e958-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="1e958-109">stepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e958-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e958-110">Tids åtgången för tids utvecklingen.</span><span class="sxs-lookup"><span data-stu-id="1e958-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1e958-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1e958-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1e958-112">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="1e958-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e958-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e958-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

