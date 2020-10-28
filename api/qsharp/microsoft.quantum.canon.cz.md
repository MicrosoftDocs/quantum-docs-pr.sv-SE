---
uid: Microsoft.Quantum.Canon.CZ
title: CZ-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728776"
---
# <a name="cz-operation"></a><span data-ttu-id="6732d-102">CZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6732d-102">CZ operation</span></span>

<span data-ttu-id="6732d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6732d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6732d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6732d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6732d-105">Använder CZ-porten (styrd-Z) till ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="6732d-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="6732d-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ där rader och kolumner ordnas som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="6732d-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6732d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="6732d-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="6732d-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6732d-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6732d-109">Kontrol lera qubit för CZ-porten.</span><span class="sxs-lookup"><span data-stu-id="6732d-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6732d-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6732d-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6732d-111">Mål-qubit för CZ-porten.</span><span class="sxs-lookup"><span data-stu-id="6732d-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6732d-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6732d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6732d-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6732d-113">Remarks</span></span>

<span data-ttu-id="6732d-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="6732d-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```