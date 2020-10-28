---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliMajIdx_
title: Funktionen _V0123TermToPauliMajIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7295b510de2621698d48d40ac28e234d0c8915eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727852"
---
# <a name="_v0123termtopaulimajidx_-function"></a><span data-ttu-id="55c81-102">Funktionen _V0123TermToPauliMajIdx_</span><span class="sxs-lookup"><span data-stu-id="55c81-102">_V0123TermToPauliMajIdx_ function</span></span>

<span data-ttu-id="55c81-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="55c81-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="55c81-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55c81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55c81-105">Konverterar en GeneratorIndex som beskriver en PQRS-term till ett uttryck ' GeneratorIndex [] ' i termer av Paulis</span><span class="sxs-lookup"><span data-stu-id="55c81-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex[]
```


## <a name="input"></a><span data-ttu-id="55c81-106">Indata</span><span class="sxs-lookup"><span data-stu-id="55c81-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="55c81-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="55c81-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="55c81-108">`GeneratorIndex` representerar en PQRS-term.</span><span class="sxs-lookup"><span data-stu-id="55c81-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="55c81-109">Utdata: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]</span><span class="sxs-lookup"><span data-stu-id="55c81-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]</span></span>

<span data-ttu-id="55c81-110">' GeneratorIndex [] ' uttrycker PQRS term som Pauli-villkor.</span><span class="sxs-lookup"><span data-stu-id="55c81-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>