---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: Funktionen _PQandPQQRTermToPauliGenIdx_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: c4de9593927b12b2387ae0b46513970308f59c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839331"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="32d23-102">Funktionen _PQandPQQRTermToPauliGenIdx_</span><span class="sxs-lookup"><span data-stu-id="32d23-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="32d23-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="32d23-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="32d23-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="32d23-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="32d23-105">Konverterar en GeneratorIndex som beskriver en PQ-eller PQQR-period till ett uttryck (GeneratorIndex []) i termer av Paul</span><span class="sxs-lookup"><span data-stu-id="32d23-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="32d23-106">Indata</span><span class="sxs-lookup"><span data-stu-id="32d23-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="32d23-107">term: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="32d23-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="32d23-108">`GeneratorIndex` representerar en PQ-eller PQQR-term.</span><span class="sxs-lookup"><span data-stu-id="32d23-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="32d23-109">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="32d23-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="32d23-110">' GeneratorIndex [] ' uttrycker PQ eller PQQR term som Pauli villkor.</span><span class="sxs-lookup"><span data-stu-id="32d23-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>