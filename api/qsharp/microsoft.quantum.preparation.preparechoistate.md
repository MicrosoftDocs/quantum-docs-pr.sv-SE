---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733219"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="a6010-102">PrepareChoiState-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a6010-102">PrepareChoiState operation</span></span>

<span data-ttu-id="a6010-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a6010-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a6010-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6010-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6010-105">Förbereder Choi – Jamiłkowski-tillstånd för en specifik åtgärd på den angivna referensen och mål registren.</span><span class="sxs-lookup"><span data-stu-id="a6010-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a6010-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a6010-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="a6010-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6010-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a6010-108">Åtgärd $ \Lambda $ vars Choi – Jamiłkowski State $J (\Lambda)/2 ^ N $ ska förberedas, där $N $ är antalet qubits som `op` fungerar.</span><span class="sxs-lookup"><span data-stu-id="a6010-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="a6010-109">Referens: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a6010-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a6010-110">Ett register över qubits som startar i $ \ket{00\cdots 0} $ State som ska användas som referens för åtgärden `op` .</span><span class="sxs-lookup"><span data-stu-id="a6010-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a6010-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a6010-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a6010-112">Ett register över qubits inlednings vis i den $ \ket{00\cdots 0} $-status som ska `op` tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a6010-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6010-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6010-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a6010-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a6010-114">Remarks</span></span>

<span data-ttu-id="a6010-115">Choi – Jamiłkowski State $J (\Lambda) $ av en Quantum-process definieras som $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ är *vectorization* för en matris $X $ i kolumn-Staplings konventionen.</span><span class="sxs-lookup"><span data-stu-id="a6010-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="a6010-116">Lär dig en klassisk Beskrivning av det här tillståndet ger fullständig information om effekterna av $ \Lambda $ som fungerar på godtyckliga ingångs tillstånd och utgör grunden för *Quantum process tomography* .</span><span class="sxs-lookup"><span data-stu-id="a6010-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="a6010-117">Se även</span><span class="sxs-lookup"><span data-stu-id="a6010-117">See Also</span></span>

- [<span data-ttu-id="a6010-118">Microsoft. Quantum. preparation. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="a6010-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="a6010-119">Microsoft. Quantum. preparation. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="a6010-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="a6010-120">Microsoft. Quantum. preparation. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="a6010-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)