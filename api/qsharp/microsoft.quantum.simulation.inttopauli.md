---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Funktionen IntToPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733702"
---
# <a name="inttopauli-function"></a><span data-ttu-id="41b0b-102">Funktionen IntToPauli</span><span class="sxs-lookup"><span data-stu-id="41b0b-102">IntToPauli function</span></span>

<span data-ttu-id="41b0b-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="41b0b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="41b0b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41b0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41b0b-105">Konverterar ett heltal till en enskild-qubit Pauli-operator.</span><span class="sxs-lookup"><span data-stu-id="41b0b-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="41b0b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="41b0b-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="41b0b-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="41b0b-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="41b0b-108">Heltal i intervallet `0..3` som ska konverteras till Pauli-operatorer.</span><span class="sxs-lookup"><span data-stu-id="41b0b-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="41b0b-109">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="41b0b-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="41b0b-110">En `Pauli` operator som angetts av `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="41b0b-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>