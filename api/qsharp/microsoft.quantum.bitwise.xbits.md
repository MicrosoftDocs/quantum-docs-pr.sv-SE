---
uid: Microsoft.Quantum.Bitwise.XBits
title: Funktionen XBits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845232"
---
# <a name="xbits-function"></a><span data-ttu-id="1cead-102">Funktionen XBits</span><span class="sxs-lookup"><span data-stu-id="1cead-102">XBits function</span></span>

<span data-ttu-id="1cead-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1cead-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1cead-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1cead-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1cead-105">Returnerar ett heltal som representerar X-bitarna för en matris med Pauli-operatorer.</span><span class="sxs-lookup"><span data-stu-id="1cead-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="1cead-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1cead-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="1cead-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1cead-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1cead-108">En matris med Pauli-operatorer som ska representeras som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="1cead-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="1cead-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1cead-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1cead-110">Ett heltal $x $ med binär representation $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, där $p _i = $0 om `paulis[i]` är `PauliI` eller `PauliZ` och där $p _i = $1 om `paulis[i]` är `PauliX` eller `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="1cead-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cead-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1cead-111">Remarks</span></span>

<span data-ttu-id="1cead-112">Funktionen kommer att utlösa om längden på `paulis` matrisen är större än 63.</span><span class="sxs-lookup"><span data-stu-id="1cead-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cead-113">Se även</span><span class="sxs-lookup"><span data-stu-id="1cead-113">See Also</span></span>

- [<span data-ttu-id="1cead-114">Microsoft. Quantum. bitvis. ZBits</span><span class="sxs-lookup"><span data-stu-id="1cead-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)