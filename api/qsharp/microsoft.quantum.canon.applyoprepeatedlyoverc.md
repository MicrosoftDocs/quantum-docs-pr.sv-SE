---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: ApplyOpRepeatedlyOverC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729412"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="50ec4-102">ApplyOpRepeatedlyOverC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="50ec4-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="50ec4-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50ec4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50ec4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50ec4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50ec4-105">Använder samma OP över ett qubit-register flera gånger.</span><span class="sxs-lookup"><span data-stu-id="50ec4-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="50ec4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="50ec4-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="50ec4-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="50ec4-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="50ec4-108">En åtgärd som ska tillämpas flera gånger på qubit-registreringen</span><span class="sxs-lookup"><span data-stu-id="50ec4-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="50ec4-109">mål: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="50ec4-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="50ec4-110">Kapslade matriser som beskriver målen för op.</span><span class="sxs-lookup"><span data-stu-id="50ec4-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="50ec4-111">Varje matris ska innehålla en lista över InTS som beskriver de qubits som ska användas.</span><span class="sxs-lookup"><span data-stu-id="50ec4-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="50ec4-112">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="50ec4-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="50ec4-113">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="50ec4-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50ec4-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50ec4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="50ec4-115">Se även</span><span class="sxs-lookup"><span data-stu-id="50ec4-115">See Also</span></span>

- [<span data-ttu-id="50ec4-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="50ec4-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)