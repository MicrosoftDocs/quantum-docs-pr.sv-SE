---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: Funktionen HTermsToGenIdx
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216021"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="87bf3-102">Funktionen HTermsToGenIdx</span><span class="sxs-lookup"><span data-stu-id="87bf3-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="87bf3-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="87bf3-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="87bf3-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="87bf3-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="87bf3-105">Konverterar ett index till en Hamiltonian-term i `HTerm[]` data format till en GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="87bf3-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="87bf3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="87bf3-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="87bf3-107">data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="87bf3-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="87bf3-108">Indata i `HTerm[]` format.</span><span class="sxs-lookup"><span data-stu-id="87bf3-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="87bf3-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="87bf3-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="87bf3-110">Ytterligare information har lagts till i GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="87bf3-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="87bf3-111">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87bf3-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87bf3-112">Index till en term i Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="87bf3-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="87bf3-113">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="87bf3-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="87bf3-114">En GeneratorIndex representerar en Hamiltonian-term som representeras av `data[idx]` , tillsammans med ytterligare information som lagts till av `termType` .</span><span class="sxs-lookup"><span data-stu-id="87bf3-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>