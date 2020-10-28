---
uid: Microsoft.Quantum.Canon.CY
title: CY-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728782"
---
# <a name="cy-operation"></a><span data-ttu-id="9f470-102">CY-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9f470-102">CY operation</span></span>

<span data-ttu-id="9f470-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f470-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f470-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f470-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f470-105">Tillämpar den kontrollerade Y-porten (CY) på ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="9f470-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="9f470-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 &-i \\ \\ 0 & 0 & i & 0 \end{align} $ $ där rader och kolumner är ordnade som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="9f470-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9f470-107">Indata</span><span class="sxs-lookup"><span data-stu-id="9f470-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="9f470-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9f470-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9f470-109">Styr qubit för CY-grinden.</span><span class="sxs-lookup"><span data-stu-id="9f470-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9f470-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9f470-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9f470-111">Mål-qubit för CY-grinden.</span><span class="sxs-lookup"><span data-stu-id="9f470-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f470-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f470-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9f470-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9f470-113">Remarks</span></span>

<span data-ttu-id="9f470-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="9f470-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```