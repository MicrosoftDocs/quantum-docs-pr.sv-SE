---
uid: Microsoft.Quantum.Canon.CZ
title: CZ-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840695"
---
# <a name="cz-operation"></a><span data-ttu-id="a0849-102">CZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a0849-102">CZ operation</span></span>

<span data-ttu-id="a0849-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a0849-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a0849-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0849-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0849-105">Använder CZ-porten (styrd-Z) till ett par med qubits.</span><span class="sxs-lookup"><span data-stu-id="a0849-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="a0849-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ där rader och kolumner ordnas som i Quantum Concepts-guiden.</span><span class="sxs-lookup"><span data-stu-id="a0849-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a0849-107">Indata</span><span class="sxs-lookup"><span data-stu-id="a0849-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a0849-108">kontroll: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a0849-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a0849-109">Kontrol lera qubit för CZ-porten.</span><span class="sxs-lookup"><span data-stu-id="a0849-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a0849-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a0849-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a0849-111">Mål-qubit för CZ-porten.</span><span class="sxs-lookup"><span data-stu-id="a0849-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0849-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0849-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a0849-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a0849-113">Remarks</span></span>

<span data-ttu-id="a0849-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="a0849-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```