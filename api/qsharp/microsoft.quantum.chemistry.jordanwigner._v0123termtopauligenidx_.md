---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: Funktionen _V0123TermToPauliGenIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727858"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="474eb-102">Funktionen _V0123TermToPauliGenIdx_</span><span class="sxs-lookup"><span data-stu-id="474eb-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="474eb-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="474eb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="474eb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="474eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="474eb-105">Konverterar en GeneratorIndex som beskriver en PQRS-term till ett uttryck ' GeneratorIndex [] ' i termer av Paulis</span><span class="sxs-lookup"><span data-stu-id="474eb-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="474eb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="474eb-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="474eb-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="474eb-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="474eb-108">`GeneratorIndex` representerar en PQRS-term.</span><span class="sxs-lookup"><span data-stu-id="474eb-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="474eb-109">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="474eb-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="474eb-110">' GeneratorIndex [] ' uttrycker PQRS term som Pauli-villkor.</span><span class="sxs-lookup"><span data-stu-id="474eb-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>