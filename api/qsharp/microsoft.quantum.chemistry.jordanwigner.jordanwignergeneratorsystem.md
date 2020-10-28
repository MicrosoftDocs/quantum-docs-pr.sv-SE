---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: Funktionen JordanWignerGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 30da4129278f83633c2cc76489c7c81304a1f565
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727765"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="33d99-102">Funktionen JordanWignerGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="33d99-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="33d99-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="33d99-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="33d99-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33d99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33d99-105">Konverterar en Hamiltonian som beskrivs av `JWOptimizedHTerms` till en `GeneratorSystem` uttryckt i termer av den `GeneratorIndex` konvention som definierats i den här filen.</span><span class="sxs-lookup"><span data-stu-id="33d99-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="33d99-106">Indata</span><span class="sxs-lookup"><span data-stu-id="33d99-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="33d99-107">data: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="33d99-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="33d99-108">Beskrivning av Hamiltonian i `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="33d99-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="33d99-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="33d99-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="33d99-110">Representation av Hamiltonian som `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="33d99-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>