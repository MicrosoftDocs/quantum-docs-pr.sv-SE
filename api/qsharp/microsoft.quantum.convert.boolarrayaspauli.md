---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Funktionen BoolArrayAsPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727600"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="a1476-102">Funktionen BoolArrayAsPauli</span><span class="sxs-lookup"><span data-stu-id="a1476-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="a1476-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a1476-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a1476-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1476-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1476-105">Med en bit-sträng returnerar en qubit Pauli-operator som representeras som en matris med qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="a1476-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a1476-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a1476-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a1476-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a1476-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a1476-108">Pauli-operator som ska användas för qubits där `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="a1476-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="a1476-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a1476-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a1476-110">Använd Pauli om bit är det här värdet.</span><span class="sxs-lookup"><span data-stu-id="a1476-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="a1476-111">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a1476-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a1476-112">Boolesk matris.</span><span class="sxs-lookup"><span data-stu-id="a1476-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a1476-113">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a1476-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="a1476-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a1476-114">Remarks</span></span>

<span data-ttu-id="a1476-115">Den booleska matrisen och Quantum-registret måste vara lika långa.</span><span class="sxs-lookup"><span data-stu-id="a1476-115">The Boolean array and the quantum register must be of equal length.</span></span>