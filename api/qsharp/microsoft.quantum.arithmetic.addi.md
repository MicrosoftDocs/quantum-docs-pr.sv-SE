---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191031"
---
# <a name="addi-operation"></a><span data-ttu-id="0a3de-102">AddI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0a3de-102">AddI operation</span></span>

<span data-ttu-id="0a3de-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0a3de-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0a3de-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0a3de-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0a3de-105">Väljer automatiskt mellan tillägg med bär och utan, beroende på register storleken för `ys` .</span><span class="sxs-lookup"><span data-stu-id="0a3de-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a3de-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0a3de-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0a3de-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0a3de-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0a3de-108">$n $-bit adderas.</span><span class="sxs-lookup"><span data-stu-id="0a3de-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0a3de-109">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0a3de-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0a3de-110">Adderas med minst $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="0a3de-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="0a3de-111">Innehåller resultatet.</span><span class="sxs-lookup"><span data-stu-id="0a3de-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a3de-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a3de-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

