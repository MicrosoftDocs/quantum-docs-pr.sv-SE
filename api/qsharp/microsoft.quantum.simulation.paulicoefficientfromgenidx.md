---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: Funktionen PauliCoefficientFromGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730910"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="ac890-102">Funktionen PauliCoefficientFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="ac890-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="ac890-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ac890-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ac890-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac890-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac890-105">Extraherar koefficienten för en Pauli term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ac890-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="ac890-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ac890-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="ac890-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ac890-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ac890-108">`GeneratorIndex` typ som kodar en Pauli-term.</span><span class="sxs-lookup"><span data-stu-id="ac890-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="ac890-109">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac890-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac890-110">Koefficienten för termen som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ac890-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>