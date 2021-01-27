---
uid: Microsoft.Quantum.Canon.CX
title: CX-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840758"
---
# <a name="cx-operation"></a><span data-ttu-id="09a11-102">CX-åtgärd</span><span class="sxs-lookup"><span data-stu-id="09a11-102">CX operation</span></span>

<span data-ttu-id="09a11-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09a11-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09a11-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09a11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09a11-105">Tillämpar den kontrollerade X (CX)-porten på ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="09a11-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="09a11-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $ där rader och kolumner är ordnade som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="09a11-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="09a11-107">Indata</span><span class="sxs-lookup"><span data-stu-id="09a11-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="09a11-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="09a11-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="09a11-109">Kontrol lera qubit för CX-grinden.</span><span class="sxs-lookup"><span data-stu-id="09a11-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="09a11-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="09a11-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="09a11-111">Mål-qubit för CX-grinden.</span><span class="sxs-lookup"><span data-stu-id="09a11-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09a11-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09a11-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="09a11-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="09a11-113">Remarks</span></span>

<span data-ttu-id="09a11-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="09a11-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="09a11-115">och för att:</span><span class="sxs-lookup"><span data-stu-id="09a11-115">and to:</span></span>

```qsharp
CNOT(control, target);
```