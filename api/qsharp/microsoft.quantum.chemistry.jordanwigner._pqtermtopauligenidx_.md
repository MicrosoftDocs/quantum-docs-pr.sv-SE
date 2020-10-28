---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: Funktionen _PQTermToPauliGenIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1f9567f327b5afc3054acbf1a615b44a54453004
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727918"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="600e1-102">Funktionen _PQTermToPauliGenIdx_</span><span class="sxs-lookup"><span data-stu-id="600e1-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="600e1-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="600e1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="600e1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="600e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="600e1-105">Konverterar en GeneratorIndex som beskriver en PQ-term till ett uttryck ' GeneratorIndex [] ' i termer av Paulis</span><span class="sxs-lookup"><span data-stu-id="600e1-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="600e1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="600e1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="600e1-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="600e1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="600e1-108">`GeneratorIndex` representerar en PQ-term.</span><span class="sxs-lookup"><span data-stu-id="600e1-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="600e1-109">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="600e1-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="600e1-110">' GeneratorIndex [] ' uttrycker PQ term som Pauli-villkor.</span><span class="sxs-lookup"><span data-stu-id="600e1-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>