---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: e9c245fb7c0cf3a6b1b98eb01cd582c325917602
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843303"
---
# <a name="comparegti-operation"></a><span data-ttu-id="466a6-102">CompareGTI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="466a6-102">CompareGTI operation</span></span>

<span data-ttu-id="466a6-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="466a6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="466a6-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="466a6-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="466a6-105">Wrapper för heltals jämförelse: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="466a6-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="466a6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="466a6-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="466a6-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="466a6-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="466a6-108">Första $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="466a6-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="466a6-109">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="466a6-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="466a6-110">Andra $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="466a6-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="466a6-111">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="466a6-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="466a6-112">Kommer att vändas om $x > y $</span><span class="sxs-lookup"><span data-stu-id="466a6-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="466a6-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="466a6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

