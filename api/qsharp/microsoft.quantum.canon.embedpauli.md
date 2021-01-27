---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Funktionen EmbedPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840525"
---
# <a name="embedpauli-function"></a><span data-ttu-id="d117e-102">Funktionen EmbedPauli</span><span class="sxs-lookup"><span data-stu-id="d117e-102">EmbedPauli function</span></span>

<span data-ttu-id="d117e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d117e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d117e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d117e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d117e-105">Med en enda-qubit Pauli-operator och indexet för en qubit returneras en Pauli-operator med en med en-operator med den aktuella indexen och `PauliI` vid alla andra index.</span><span class="sxs-lookup"><span data-stu-id="d117e-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="d117e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d117e-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="d117e-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d117e-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d117e-108">En qubit Pauli-operatör som ska placeras på den aktuella platsen.</span><span class="sxs-lookup"><span data-stu-id="d117e-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="d117e-109">plats: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d117e-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d117e-110">Ett index som `output[location] == pauli` , där `output` är resultatet av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="d117e-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="d117e-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d117e-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d117e-112">Längden på matrisen som ska returneras.</span><span class="sxs-lookup"><span data-stu-id="d117e-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="d117e-113">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d117e-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="d117e-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="d117e-114">Example</span></span>

<span data-ttu-id="d117e-115">Så här hämtar du matrisen `[PauliI, PauliI, PauliX, PauliI]` :</span><span class="sxs-lookup"><span data-stu-id="d117e-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```