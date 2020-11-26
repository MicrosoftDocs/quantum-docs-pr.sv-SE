---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226085"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="2b8e8-102">_DeltaParityCNOTbitstring funktion</span><span class="sxs-lookup"><span data-stu-id="2b8e8-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="2b8e8-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="2b8e8-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="2b8e8-105">Klassiskt bearbetnings steg av `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="2b8e8-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="2b8e8-106">Detta beräknar en lista över kontroll-qubits för att utvärdera paritets skillnaden mellan två PQRS... villkor för den jämna längden.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="2b8e8-107">Indata</span><span class="sxs-lookup"><span data-stu-id="2b8e8-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="2b8e8-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2b8e8-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="2b8e8-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2b8e8-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="2b8e8-110">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="2b8e8-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="2b8e8-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2b8e8-111">Remarks</span></span>

<span data-ttu-id="2b8e8-112">Detta förutsätter att längden på termerna är jämn.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="2b8e8-113">Visar en lista över kontroller för paritets skillnader mellan två termer.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="2b8e8-114">Detta förutsätter att indatalist-listorna är sorterade i stigande ordning.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-114">This assumes that the input lists is sorted in ascending order.</span></span>