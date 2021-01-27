---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Funktionen PauliArrayAsInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832713"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="4e120-102">Funktionen PauliArrayAsInt</span><span class="sxs-lookup"><span data-stu-id="4e120-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="4e120-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4e120-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4e120-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4e120-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4e120-105">Kodar en qubit Pauli-operatör som representeras som en matris med qubit Pauli-operatörer till ett heltal.</span><span class="sxs-lookup"><span data-stu-id="4e120-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="4e120-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4e120-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="4e120-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4e120-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="4e120-108">En matris med högst 31 Single-qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="4e120-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="4e120-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e120-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e120-110">Ett heltal som identifierar unikt `paulis` , enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="4e120-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e120-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4e120-111">Remarks</span></span>

<span data-ttu-id="4e120-112">Varje Pauli-operatör kan kodas med två bitar: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="4e120-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="4e120-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4e120-113">\end{align} $$</span></span>

<span data-ttu-id="4e120-114">Med en matris med Pauli `[P0, ..., Pn]` -operatörer returnerar den här funktionen ett heltal med binär expansion som bildas genom att sammanfoga mappningarna för varje Pauli-operator i big-endian-ordningen `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="4e120-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>