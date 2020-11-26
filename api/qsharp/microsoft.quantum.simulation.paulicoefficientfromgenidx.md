---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: Funktionen PauliCoefficientFromGenIdx
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 59ddadabb5c77cdb0d2e3620a09433992e85f663
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225065"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="9b06b-102">Funktionen PauliCoefficientFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="9b06b-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="9b06b-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9b06b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9b06b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b06b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b06b-105">Extraherar koefficienten för en Pauli term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9b06b-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="9b06b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9b06b-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="9b06b-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9b06b-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9b06b-108">`GeneratorIndex` typ som kodar en Pauli-term.</span><span class="sxs-lookup"><span data-stu-id="9b06b-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="9b06b-109">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b06b-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b06b-110">Koefficienten för termen som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9b06b-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>