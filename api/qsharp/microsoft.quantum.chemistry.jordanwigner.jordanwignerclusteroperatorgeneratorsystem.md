---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: Funktionen JordanWignerClusterOperatorGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: c75dcd655dafb7048f61f4b07b852cc5f437275d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727795"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a><span data-ttu-id="3c85a-102">Funktionen JordanWignerClusterOperatorGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="3c85a-102">JordanWignerClusterOperatorGeneratorSystem function</span></span>

<span data-ttu-id="3c85a-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3c85a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3c85a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c85a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c85a-105">Konverterar en Hamiltonian som beskrivs av `JWOptimizedHTerms` till en `GeneratorSystem` uttryckt i termer av den `GeneratorIndex` konvention som definierats i den här filen.</span><span class="sxs-lookup"><span data-stu-id="3c85a-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="3c85a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3c85a-106">Input</span></span>

### <a name="data--jordanwignerinputstate"></a><span data-ttu-id="3c85a-107">data: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="3c85a-107">data : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="3c85a-108">Beskrivning av Hamiltonian i `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="3c85a-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="3c85a-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3c85a-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3c85a-110">Representation av Hamiltonian som `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="3c85a-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>