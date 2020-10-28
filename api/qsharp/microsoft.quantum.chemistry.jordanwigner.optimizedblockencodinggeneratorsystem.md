---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: Funktionen OptimizedBlockEncodingGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: c3e48cb5dde36b694a5b16f25333cf0dad6c0f61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727726"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="8168e-102">Funktionen OptimizedBlockEncodingGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="8168e-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="8168e-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="8168e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="8168e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8168e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8168e-105">Konverterar en Hamiltonian som beskrivs av `JWOptimizedHTerms` till en `GeneratorSystem` uttryckt i Pauli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="8168e-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="8168e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8168e-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="8168e-107">data: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="8168e-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="8168e-108">Beskrivning av Hamiltonian i `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="8168e-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="8168e-109">Utdata: [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="8168e-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="8168e-110">Representation av Hamiltonian som `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="8168e-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>