---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Funktionen BoolArrayAsPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214287"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="21588-102">Funktionen BoolArrayAsPauli</span><span class="sxs-lookup"><span data-stu-id="21588-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="21588-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="21588-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="21588-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21588-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21588-105">Med en bit-sträng returnerar en qubit Pauli-operator som representeras som en matris med qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="21588-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="21588-106">Indata</span><span class="sxs-lookup"><span data-stu-id="21588-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="21588-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="21588-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="21588-108">Pauli-operator som ska användas för qubits där `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="21588-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="21588-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21588-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21588-110">Använd Pauli om bit är det här värdet.</span><span class="sxs-lookup"><span data-stu-id="21588-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="21588-111">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="21588-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="21588-112">Boolesk matris.</span><span class="sxs-lookup"><span data-stu-id="21588-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="21588-113">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="21588-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="21588-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="21588-114">Remarks</span></span>

<span data-ttu-id="21588-115">Den booleska matrisen och Quantum-registret måste vara lika långa.</span><span class="sxs-lookup"><span data-stu-id="21588-115">The Boolean array and the quantum register must be of equal length.</span></span>