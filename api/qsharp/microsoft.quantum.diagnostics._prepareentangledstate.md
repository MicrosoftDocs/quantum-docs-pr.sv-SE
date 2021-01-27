---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830971"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="3a90e-102">_prepareEntangledState åtgärd</span><span class="sxs-lookup"><span data-stu-id="3a90e-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="3a90e-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3a90e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3a90e-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3a90e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3a90e-105">Med två register, förbereder maximally Entangled-statusen mellan varje par av qubits i respektive register.</span><span class="sxs-lookup"><span data-stu-id="3a90e-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="3a90e-106">Alla qubits måste starta i ⟩-läget | 0.</span><span class="sxs-lookup"><span data-stu-id="3a90e-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="3a90e-107">Resultatet är att motsvarande par qubits från varje register finns i $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="3a90e-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3a90e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="3a90e-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="3a90e-109">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3a90e-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3a90e-110">En qubit-matris i $ \ket{0\cdots $ State</span><span class="sxs-lookup"><span data-stu-id="3a90e-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="3a90e-111">höger: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3a90e-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3a90e-112">En qubit-matris i $ \ket{0\cdots $ State</span><span class="sxs-lookup"><span data-stu-id="3a90e-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a90e-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a90e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

