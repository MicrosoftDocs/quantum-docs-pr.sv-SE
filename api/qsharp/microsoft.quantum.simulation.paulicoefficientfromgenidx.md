---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: Funktionen PauliCoefficientFromGenIdx
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: eb4f7a538e85ade4b095aa3ea5eab4448eda2491
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848001"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="d926b-102">Funktionen PauliCoefficientFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="d926b-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="d926b-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d926b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d926b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d926b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d926b-105">Extraherar koefficienten för en Pauli term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="d926b-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="d926b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d926b-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="d926b-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d926b-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d926b-108">`GeneratorIndex` typ som kodar en Pauli-term.</span><span class="sxs-lookup"><span data-stu-id="d926b-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="d926b-109">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d926b-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d926b-110">Koefficienten för termen som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="d926b-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>