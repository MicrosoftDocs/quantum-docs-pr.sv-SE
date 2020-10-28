---
uid: Microsoft.Quantum.Canon.CX
title: CX-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728788"
---
# <a name="cx-operation"></a><span data-ttu-id="98c9e-102">CX-åtgärd</span><span class="sxs-lookup"><span data-stu-id="98c9e-102">CX operation</span></span>

<span data-ttu-id="98c9e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98c9e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98c9e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98c9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98c9e-105">Tillämpar den kontrollerade X (CX)-porten på ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="98c9e-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="98c9e-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $ där rader och kolumner är ordnade som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="98c9e-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="98c9e-107">Indata</span><span class="sxs-lookup"><span data-stu-id="98c9e-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="98c9e-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="98c9e-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="98c9e-109">Kontrol lera qubit för CX-grinden.</span><span class="sxs-lookup"><span data-stu-id="98c9e-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="98c9e-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="98c9e-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="98c9e-111">Mål-qubit för CX-grinden.</span><span class="sxs-lookup"><span data-stu-id="98c9e-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98c9e-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98c9e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="98c9e-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="98c9e-113">Remarks</span></span>

<span data-ttu-id="98c9e-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="98c9e-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="98c9e-115">och för att:</span><span class="sxs-lookup"><span data-stu-id="98c9e-115">and to:</span></span>

```qsharp
CNOT(control, target);
```