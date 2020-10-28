---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726421"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="6414b-102">_DeltaParityCNOTbitstring funktion</span><span class="sxs-lookup"><span data-stu-id="6414b-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="6414b-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6414b-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="6414b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6414b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6414b-105">Klassiskt bearbetnings steg av `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="6414b-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="6414b-106">Detta beräknar en lista över kontroll-qubits för att utvärdera paritets skillnaden mellan två PQRS... villkor för den jämna längden.</span><span class="sxs-lookup"><span data-stu-id="6414b-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="6414b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="6414b-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="6414b-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6414b-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="6414b-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6414b-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="6414b-110">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="6414b-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="6414b-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6414b-111">Remarks</span></span>

<span data-ttu-id="6414b-112">Detta förutsätter att längden på termerna är jämn.</span><span class="sxs-lookup"><span data-stu-id="6414b-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="6414b-113">Visar en lista över kontroller för paritets skillnader mellan två termer.</span><span class="sxs-lookup"><span data-stu-id="6414b-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="6414b-114">Detta förutsätter att indatalist-listorna är sorterade i stigande ordning.</span><span class="sxs-lookup"><span data-stu-id="6414b-114">This assumes that the input lists is sorted in ascending order.</span></span>