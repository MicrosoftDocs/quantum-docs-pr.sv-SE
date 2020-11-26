---
uid: Microsoft.Quantum.Canon.CZ
title: CZ-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207215"
---
# <a name="cz-operation"></a><span data-ttu-id="37fee-102">CZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="37fee-102">CZ operation</span></span>

<span data-ttu-id="37fee-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37fee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37fee-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37fee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37fee-105">Använder CZ-porten (styrd-Z) till ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="37fee-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="37fee-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ där rader och kolumner ordnas som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="37fee-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="37fee-107">Indata</span><span class="sxs-lookup"><span data-stu-id="37fee-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="37fee-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="37fee-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="37fee-109">Kontrol lera qubit för CZ-porten.</span><span class="sxs-lookup"><span data-stu-id="37fee-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="37fee-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="37fee-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="37fee-111">Mål-qubit för CZ-porten.</span><span class="sxs-lookup"><span data-stu-id="37fee-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37fee-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37fee-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="37fee-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="37fee-113">Remarks</span></span>

<span data-ttu-id="37fee-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="37fee-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```