---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: Funktionen HTermsToGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728137"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="9a4ab-102">Funktionen HTermsToGenIdx</span><span class="sxs-lookup"><span data-stu-id="9a4ab-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="9a4ab-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9a4ab-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="9a4ab-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a4ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a4ab-105">Konverterar ett index till en Hamiltonian-term i `HTerm[]` data format till en GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="9a4ab-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="9a4ab-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9a4ab-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="9a4ab-107">data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="9a4ab-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="9a4ab-108">Indata i `HTerm[]` format.</span><span class="sxs-lookup"><span data-stu-id="9a4ab-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="9a4ab-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9a4ab-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9a4ab-110">Ytterligare information har lagts till i GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="9a4ab-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="9a4ab-111">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a4ab-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a4ab-112">Index till en term i Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="9a4ab-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="9a4ab-113">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9a4ab-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9a4ab-114">En GeneratorIndex representerar en Hamiltonian-term som representeras av `data[idx]` , tillsammans med ytterligare information som lagts till av `termType` .</span><span class="sxs-lookup"><span data-stu-id="9a4ab-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>