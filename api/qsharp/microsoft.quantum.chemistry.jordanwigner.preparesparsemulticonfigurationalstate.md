---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: PrepareSparseMultiConfigurationalState-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727705"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="83cc8-102">PrepareSparseMultiConfigurationalState-åtgärd</span><span class="sxs-lookup"><span data-stu-id="83cc8-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="83cc8-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="83cc8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="83cc8-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83cc8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83cc8-105">Sparse-förberedelse för flera konfigurationer av utvärderings tillstånd genom att lägga till excitations i första utvärderings tillstånd.</span><span class="sxs-lookup"><span data-stu-id="83cc8-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="83cc8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="83cc8-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="83cc8-107">initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83cc8-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="83cc8-108">Enhetligt läge för att förbereda den första utvärderings versionen.</span><span class="sxs-lookup"><span data-stu-id="83cc8-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="83cc8-109">excitations: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="83cc8-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="83cc8-110">Excitations av det första utvärderings stadiet som representeras av amplituden för excitation och qubit index som excitation fungerar på.</span><span class="sxs-lookup"><span data-stu-id="83cc8-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="83cc8-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="83cc8-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="83cc8-112">Qubits för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="83cc8-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83cc8-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83cc8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

