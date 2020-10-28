---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: Funktionen HTermToGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728128"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="22986-102">Funktionen HTermToGenIdx</span><span class="sxs-lookup"><span data-stu-id="22986-102">HTermToGenIdx function</span></span>

<span data-ttu-id="22986-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="22986-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="22986-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22986-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22986-105">Konverterar en Hamiltonian-term i `HTerm` data format till en GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="22986-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="22986-106">Indata</span><span class="sxs-lookup"><span data-stu-id="22986-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="22986-107">term: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="22986-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="22986-108">Indata i `HTerm` format.</span><span class="sxs-lookup"><span data-stu-id="22986-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="22986-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="22986-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="22986-110">Ytterligare information har lagts till i GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="22986-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="22986-111">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="22986-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="22986-112">En GeneratorIndex representerar en Hamiltonian-term som representeras av `term` , tillsammans med ytterligare information som lagts till av `termType` .</span><span class="sxs-lookup"><span data-stu-id="22986-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>