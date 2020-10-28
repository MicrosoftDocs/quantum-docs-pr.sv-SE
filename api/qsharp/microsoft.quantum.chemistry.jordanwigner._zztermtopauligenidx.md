---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: f8a173e2adb4494a08b48158a010f264562bbaa6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727831"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="6d667-102">_ZZTermToPauliGenIdx funktion</span><span class="sxs-lookup"><span data-stu-id="6d667-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="6d667-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6d667-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6d667-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d667-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d667-105">Konverterar en GeneratorIndex som beskriver en ZZ-term till ett uttryck ' GeneratorIndex [] ' i termer av Paulis.</span><span class="sxs-lookup"><span data-stu-id="6d667-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="6d667-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6d667-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="6d667-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6d667-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6d667-108">`GeneratorIndex` representerar en ZZ-term.</span><span class="sxs-lookup"><span data-stu-id="6d667-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="6d667-109">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="6d667-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="6d667-110">' GeneratorIndex [] ' uttrycker ZZ term som Pauli-villkor.</span><span class="sxs-lookup"><span data-stu-id="6d667-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>