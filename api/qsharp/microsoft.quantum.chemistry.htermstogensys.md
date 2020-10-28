---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: Funktionen HTermsToGenSys
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728131"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="eddb3-102">Funktionen HTermsToGenSys</span><span class="sxs-lookup"><span data-stu-id="eddb3-102">HTermsToGenSys function</span></span>

<span data-ttu-id="eddb3-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="eddb3-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="eddb3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eddb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eddb3-105">Konverterar ett Hamiltonian i `HTerm[]` data format till en GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="eddb3-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="eddb3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eddb3-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="eddb3-107">data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="eddb3-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="eddb3-108">Indata i `HTerm[]` format.</span><span class="sxs-lookup"><span data-stu-id="eddb3-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="eddb3-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="eddb3-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="eddb3-110">Ytterligare information har lagts till i GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="eddb3-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="eddb3-111">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="eddb3-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="eddb3-112">En GeneratorSystem som representerar en Hamiltonian som representeras av indata `data` .</span><span class="sxs-lookup"><span data-stu-id="eddb3-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>