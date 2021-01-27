---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Funktionen ArrangedQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841084"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="8a362-102">Funktionen ArrangedQubits</span><span class="sxs-lookup"><span data-stu-id="8a362-102">ArrangedQubits function</span></span>

<span data-ttu-id="8a362-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a362-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a362-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a362-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a362-105">Arrangera kontroll, mål och hjälper qubits enligt ett index</span><span class="sxs-lookup"><span data-stu-id="8a362-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="8a362-106">Description</span><span class="sxs-lookup"><span data-stu-id="8a362-106">Description</span></span>

<span data-ttu-id="8a362-107">Returnerar en qubit-matris med målet vid index 0 och kontroll i index 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="8a362-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="8a362-108">Hjälpens qubits infogas på alla andra positioner i matrisen.</span><span class="sxs-lookup"><span data-stu-id="8a362-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="8a362-109">Indata</span><span class="sxs-lookup"><span data-stu-id="8a362-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="8a362-110">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a362-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="8a362-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8a362-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="8a362-112">hjälp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a362-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="8a362-113">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a362-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

