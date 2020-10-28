---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: Funktionen _ZTermToPauliMajIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 890e60c4b7c5bc474c9f00b59dac6bfddb0e891b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727834"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="197a0-102">Funktionen _ZTermToPauliMajIdx_</span><span class="sxs-lookup"><span data-stu-id="197a0-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="197a0-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="197a0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="197a0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="197a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="197a0-105">Konverterar en GeneratorIndex som beskriver en Z-term till ett uttryck ' GeneratorIndex [] ' i termer av Paul '.</span><span class="sxs-lookup"><span data-stu-id="197a0-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="197a0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="197a0-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="197a0-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="197a0-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="197a0-108">`GeneratorIndex` representerar en Z-period.</span><span class="sxs-lookup"><span data-stu-id="197a0-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="197a0-109">Utdata: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="197a0-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="197a0-110">"GeneratorIndex []" uttrycker Z-termen som Pauli villkor.</span><span class="sxs-lookup"><span data-stu-id="197a0-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>