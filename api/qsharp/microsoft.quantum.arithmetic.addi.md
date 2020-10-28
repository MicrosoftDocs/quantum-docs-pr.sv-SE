---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731894"
---
# <a name="addi-operation"></a><span data-ttu-id="ee374-102">AddI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ee374-102">AddI operation</span></span>

<span data-ttu-id="ee374-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ee374-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ee374-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee374-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee374-105">Väljer automatiskt mellan tillägg med bär och utan, beroende på register storleken för `ys` .</span><span class="sxs-lookup"><span data-stu-id="ee374-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ee374-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ee374-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ee374-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ee374-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ee374-108">$n $-bit adderas.</span><span class="sxs-lookup"><span data-stu-id="ee374-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ee374-109">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ee374-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ee374-110">Adderas med minst $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="ee374-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="ee374-111">Innehåller resultatet.</span><span class="sxs-lookup"><span data-stu-id="ee374-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee374-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee374-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

