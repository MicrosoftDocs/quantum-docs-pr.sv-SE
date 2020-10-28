---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Funktionen ArrangedQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728947"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="96fad-102">Funktionen ArrangedQubits</span><span class="sxs-lookup"><span data-stu-id="96fad-102">ArrangedQubits function</span></span>

<span data-ttu-id="96fad-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="96fad-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="96fad-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96fad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96fad-105">Arrangera kontroll, mål och hjälper qubits enligt ett index</span><span class="sxs-lookup"><span data-stu-id="96fad-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="96fad-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96fad-106">Description</span></span>

<span data-ttu-id="96fad-107">Returnerar en qubit-matris med målet vid index 0 och kontroll i index 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="96fad-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="96fad-108">Hjälpens qubits infogas på alla andra positioner i matrisen.</span><span class="sxs-lookup"><span data-stu-id="96fad-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="96fad-109">Indata</span><span class="sxs-lookup"><span data-stu-id="96fad-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="96fad-110">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96fad-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="96fad-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="96fad-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="96fad-112">hjälp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96fad-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="96fad-113">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96fad-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

