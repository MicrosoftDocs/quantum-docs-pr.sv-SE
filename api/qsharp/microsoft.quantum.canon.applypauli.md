---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729406"
---
# <a name="applypauli-operation"></a><span data-ttu-id="6f2a1-102">ApplyPauli-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6f2a1-102">ApplyPauli operation</span></span>

<span data-ttu-id="6f2a1-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6f2a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6f2a1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f2a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f2a1-105">Med en qubit Pauli-operatör tillämpas motsvarande åtgärd i en register.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6f2a1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6f2a1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="6f2a1-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="6f2a1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="6f2a1-108">En qubit Pauli-operatör som representeras som en matris med qubit Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6f2a1-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6f2a1-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6f2a1-110">Registrera dig för att tillämpa den aktuella Pauli-åtgärden på.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f2a1-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f2a1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

