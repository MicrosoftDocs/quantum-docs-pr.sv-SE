---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210581"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="44a15-102">PrepareChoiState-åtgärd</span><span class="sxs-lookup"><span data-stu-id="44a15-102">PrepareChoiState operation</span></span>

<span data-ttu-id="44a15-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="44a15-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="44a15-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44a15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44a15-105">Förbereder Choi – Jamiołkowski-tillstånd för en specifik åtgärd på den angivna referensen och mål registren.</span><span class="sxs-lookup"><span data-stu-id="44a15-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="44a15-106">Indata</span><span class="sxs-lookup"><span data-stu-id="44a15-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="44a15-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44a15-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="44a15-108">Åtgärd $ \Lambda $ vars Choi – Jamiołkowski State $J (\Lambda)/2 ^ N $ ska förberedas, där $N $ är antalet qubits som `op` fungerar.</span><span class="sxs-lookup"><span data-stu-id="44a15-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="44a15-109">Referens: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44a15-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44a15-110">Ett register över qubits som startar i $ \ket{00\cdots 0} $ State som ska användas som referens för åtgärden `op` .</span><span class="sxs-lookup"><span data-stu-id="44a15-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="44a15-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44a15-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44a15-112">Ett register över qubits inlednings vis i den $ \ket{00\cdots 0} $-status som ska `op` tillämpas.</span><span class="sxs-lookup"><span data-stu-id="44a15-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44a15-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44a15-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="44a15-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="44a15-114">Remarks</span></span>

<span data-ttu-id="44a15-115">Choi – Jamiłkowski State $J (\Lambda) $ av en Quantum-process definieras som $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ är *vectorization* för en matris $X $ i kolumn-Staplings konventionen.</span><span class="sxs-lookup"><span data-stu-id="44a15-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="44a15-116">Lär dig en klassisk Beskrivning av det här tillståndet ger fullständig information om effekterna av $ \Lambda $ som fungerar på godtyckliga ingångs tillstånd och utgör grunden för *Quantum process tomography*.</span><span class="sxs-lookup"><span data-stu-id="44a15-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="44a15-117">Se även</span><span class="sxs-lookup"><span data-stu-id="44a15-117">See Also</span></span>

- [<span data-ttu-id="44a15-118">Microsoft. Quantum. preparation. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="44a15-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="44a15-119">Microsoft. Quantum. preparation. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="44a15-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="44a15-120">Microsoft. Quantum. preparation. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="44a15-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)