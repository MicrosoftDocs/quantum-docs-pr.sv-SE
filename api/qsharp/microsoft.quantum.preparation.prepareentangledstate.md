---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732174"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="eea5b-102">PrepareEntangledState-åtgärd</span><span class="sxs-lookup"><span data-stu-id="eea5b-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="eea5b-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="eea5b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="eea5b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eea5b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eea5b-105">Entangles två qubit-register.</span><span class="sxs-lookup"><span data-stu-id="eea5b-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="eea5b-106">Med två register, förbereder maximally Entangled State $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ mellan varje par av qubits i respektive register, förutsatt att varje register startar i $-\ket{0\cdots 0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="eea5b-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eea5b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="eea5b-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="eea5b-108">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eea5b-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eea5b-109">En qubit-matris i $ \ket{0\cdots $ State</span><span class="sxs-lookup"><span data-stu-id="eea5b-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="eea5b-110">höger: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eea5b-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eea5b-111">En qubit-matris i $ \ket{0\cdots $ State</span><span class="sxs-lookup"><span data-stu-id="eea5b-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="eea5b-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eea5b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

