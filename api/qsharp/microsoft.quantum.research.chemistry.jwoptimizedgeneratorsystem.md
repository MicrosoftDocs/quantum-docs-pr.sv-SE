---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: Funktionen JWOptimizedGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 8e4c06b9447a2e5838cced876febee03d1af5315
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726391"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="c1520-102">Funktionen JWOptimizedGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="c1520-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="c1520-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c1520-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c1520-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1520-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1520-105">Konverterar en Hamiltonian som beskrivs av `JWOptimizedHTerms` till en `GeneratorSystem` uttryckt i termer av den `GeneratorIndex` konvention som definierats i den här filen.</span><span class="sxs-lookup"><span data-stu-id="c1520-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="c1520-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c1520-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="c1520-107">data: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="c1520-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="c1520-108">Beskrivning av Hamiltonian i `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="c1520-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="c1520-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c1520-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c1520-110">Representation av Hamiltonian som `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="c1520-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>