---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: Funktionen _PQTermToPauliMajIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b75e9b61e05d6451bab378108c75b10334ac1e44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727912"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="b4dde-102">Funktionen _PQTermToPauliMajIdx_</span><span class="sxs-lookup"><span data-stu-id="b4dde-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="b4dde-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b4dde-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b4dde-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4dde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4dde-105">Konverterar en GeneratorIndex som beskriver en PQ-term till ett uttryck ' GeneratorIndex [] ' i termer av Paulis</span><span class="sxs-lookup"><span data-stu-id="b4dde-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="b4dde-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b4dde-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="b4dde-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b4dde-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b4dde-108">`GeneratorIndex` representerar en PQ-term.</span><span class="sxs-lookup"><span data-stu-id="b4dde-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="b4dde-109">Utdata: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="b4dde-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="b4dde-110">' GeneratorIndex [] ' uttrycker PQ term som Pauli-villkor.</span><span class="sxs-lookup"><span data-stu-id="b4dde-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>