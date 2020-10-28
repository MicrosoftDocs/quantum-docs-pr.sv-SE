---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727399"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="c9695-102">_prepareEntangledState åtgärd</span><span class="sxs-lookup"><span data-stu-id="c9695-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="c9695-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c9695-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c9695-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9695-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9695-105">Med två register, förbereder maximally Entangled-statusen mellan varje par av qubits i respektive register.</span><span class="sxs-lookup"><span data-stu-id="c9695-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="c9695-106">Alla qubits måste starta i ⟩-läget | 0.</span><span class="sxs-lookup"><span data-stu-id="c9695-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="c9695-107">Resultatet är att motsvarande par qubits från varje register finns i $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="c9695-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c9695-108">Indata</span><span class="sxs-lookup"><span data-stu-id="c9695-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="c9695-109">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c9695-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c9695-110">En qubit-matris i $ \ket{0\cdots $ State</span><span class="sxs-lookup"><span data-stu-id="c9695-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="c9695-111">höger: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c9695-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c9695-112">En qubit-matris i $ \ket{0\cdots $ State</span><span class="sxs-lookup"><span data-stu-id="c9695-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9695-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9695-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

