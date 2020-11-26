---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223484"
---
# <a name="comparegti-operation"></a><span data-ttu-id="04666-102">CompareGTI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="04666-102">CompareGTI operation</span></span>

<span data-ttu-id="04666-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="04666-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="04666-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="04666-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="04666-105">Wrapper för heltals jämförelse: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="04666-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="04666-106">Indata</span><span class="sxs-lookup"><span data-stu-id="04666-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="04666-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="04666-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="04666-108">Första $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="04666-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="04666-109">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="04666-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="04666-110">Andra $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="04666-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="04666-111">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="04666-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="04666-112">Kommer att vändas om $x > y $</span><span class="sxs-lookup"><span data-stu-id="04666-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="04666-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04666-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

