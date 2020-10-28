---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: Funktionen _PQandPQQRTermToPauliGenIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 44a6d6b63d2f6bc8b628603e78931570d1ec22eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727930"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="912b3-102">Funktionen _PQandPQQRTermToPauliGenIdx_</span><span class="sxs-lookup"><span data-stu-id="912b3-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="912b3-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="912b3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="912b3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="912b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="912b3-105">Konverterar en GeneratorIndex som beskriver en PQ-eller PQQR-period till ett uttryck (GeneratorIndex []) i termer av Paul</span><span class="sxs-lookup"><span data-stu-id="912b3-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="912b3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="912b3-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="912b3-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="912b3-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="912b3-108">`GeneratorIndex` representerar en PQ-eller PQQR-term.</span><span class="sxs-lookup"><span data-stu-id="912b3-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="912b3-109">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="912b3-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="912b3-110">' GeneratorIndex [] ' uttrycker PQ eller PQQR term som Pauli villkor.</span><span class="sxs-lookup"><span data-stu-id="912b3-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>