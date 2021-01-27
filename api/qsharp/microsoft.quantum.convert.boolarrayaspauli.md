---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: Funktionen BoolArrayAsPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834239"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="e18b8-102">Funktionen BoolArrayAsPauli</span><span class="sxs-lookup"><span data-stu-id="e18b8-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="e18b8-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e18b8-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e18b8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e18b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e18b8-105">Med en bit-sträng returnerar en qubit Pauli-operator som representeras som en matris med qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="e18b8-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="e18b8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e18b8-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="e18b8-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e18b8-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e18b8-108">Pauli-operator som ska användas för qubits där `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="e18b8-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="e18b8-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e18b8-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e18b8-110">Använd Pauli om bit är det här värdet.</span><span class="sxs-lookup"><span data-stu-id="e18b8-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="e18b8-111">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e18b8-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="e18b8-112">Boolesk matris.</span><span class="sxs-lookup"><span data-stu-id="e18b8-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e18b8-113">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e18b8-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="e18b8-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e18b8-114">Remarks</span></span>

<span data-ttu-id="e18b8-115">Den booleska matrisen och Quantum-registret måste vara lika långa.</span><span class="sxs-lookup"><span data-stu-id="e18b8-115">The Boolean array and the quantum register must be of equal length.</span></span>