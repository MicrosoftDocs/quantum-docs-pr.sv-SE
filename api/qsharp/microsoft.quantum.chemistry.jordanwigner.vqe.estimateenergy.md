---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727663"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="d8310-102">EstimateEnergy-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d8310-102">EstimateEnergy operation</span></span>

<span data-ttu-id="d8310-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="d8310-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="d8310-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8310-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8310-105">Beräknar en molekyls energi genom att summera den energi som tillförs av de enskilda Jordan-Wigners villkoren.</span><span class="sxs-lookup"><span data-stu-id="d8310-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="d8310-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d8310-106">Description</span></span>

<span data-ttu-id="d8310-107">Den här åtgärden förlitar sig implicit på den nedrullningsbara indexerings konventionen.</span><span class="sxs-lookup"><span data-stu-id="d8310-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="d8310-108">Indata</span><span class="sxs-lookup"><span data-stu-id="d8310-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="d8310-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="d8310-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="d8310-110">Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="d8310-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="d8310-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8310-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8310-112">Antalet prover som ska användas för uppskattning av termen förväntningar.</span><span class="sxs-lookup"><span data-stu-id="d8310-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="d8310-113">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8310-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8310-114">Den beräknade energin för molekylen</span><span class="sxs-lookup"><span data-stu-id="d8310-114">The estimated energy of the molecule</span></span>