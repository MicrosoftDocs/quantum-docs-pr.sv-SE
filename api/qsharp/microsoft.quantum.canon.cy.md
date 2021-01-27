---
uid: Microsoft.Quantum.Canon.CY
title: CY-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840742"
---
# <a name="cy-operation"></a><span data-ttu-id="8c98a-102">CY-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8c98a-102">CY operation</span></span>

<span data-ttu-id="8c98a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c98a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c98a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c98a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c98a-105">Tillämpar den kontrollerade Y-porten (CY) på ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="8c98a-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="8c98a-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 &-i \\ \\ 0 & 0 & i & 0 \end{align} $ $ där rader och kolumner är ordnade som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="8c98a-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8c98a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="8c98a-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="8c98a-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8c98a-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8c98a-109">Styr qubit för CY-grinden.</span><span class="sxs-lookup"><span data-stu-id="8c98a-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8c98a-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8c98a-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8c98a-111">Mål-qubit för CY-grinden.</span><span class="sxs-lookup"><span data-stu-id="8c98a-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c98a-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c98a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8c98a-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8c98a-113">Remarks</span></span>

<span data-ttu-id="8c98a-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="8c98a-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```