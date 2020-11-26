---
uid: Microsoft.Quantum.Bitwise.ZBits
title: Funktionen ZBits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219455"
---
# <a name="zbits-function"></a><span data-ttu-id="99418-102">Funktionen ZBits</span><span class="sxs-lookup"><span data-stu-id="99418-102">ZBits function</span></span>

<span data-ttu-id="99418-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="99418-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="99418-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="99418-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="99418-105">Returnerar ett heltal som representerar Z-bitarna för en matris med Pauli-operatorer.</span><span class="sxs-lookup"><span data-stu-id="99418-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="99418-106">Indata</span><span class="sxs-lookup"><span data-stu-id="99418-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="99418-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="99418-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="99418-108">En matris med Pauli-operatorer som ska representeras som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="99418-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="99418-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99418-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99418-110">Ett heltal $x $ med binär representation $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, där $p _i = $0 om `paulis[i]` är `PauliI` eller `PauliX` och där $p _i = $1 om `paulis[i]` är `PauliY` eller `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="99418-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="99418-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="99418-111">Remarks</span></span>

<span data-ttu-id="99418-112">Funktionen kommer att utlösa om längden på `paulis` matrisen är större än 63.</span><span class="sxs-lookup"><span data-stu-id="99418-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="99418-113">Se även</span><span class="sxs-lookup"><span data-stu-id="99418-113">See Also</span></span>

- [<span data-ttu-id="99418-114">Microsoft. Quantum. bitvis. XBits</span><span class="sxs-lookup"><span data-stu-id="99418-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)