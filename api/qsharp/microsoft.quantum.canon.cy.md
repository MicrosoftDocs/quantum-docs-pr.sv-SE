---
uid: Microsoft.Quantum.Canon.CY
title: CY-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216582"
---
# <a name="cy-operation"></a><span data-ttu-id="4a953-102">CY-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4a953-102">CY operation</span></span>

<span data-ttu-id="4a953-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a953-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a953-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a953-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a953-105">Tillämpar den kontrollerade Y-porten (CY) på ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="4a953-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="4a953-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 &-i \\ \\ 0 & 0 & i & 0 \end{align} $ $ där rader och kolumner är ordnade som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="4a953-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4a953-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4a953-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="4a953-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4a953-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4a953-109">Styr qubit för CY-grinden.</span><span class="sxs-lookup"><span data-stu-id="4a953-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4a953-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4a953-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4a953-111">Mål-qubit för CY-grinden.</span><span class="sxs-lookup"><span data-stu-id="4a953-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a953-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a953-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a953-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4a953-113">Remarks</span></span>

<span data-ttu-id="4a953-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="4a953-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```