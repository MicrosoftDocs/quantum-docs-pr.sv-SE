---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 4e7f43f88654f10ece4f9c30c5bfde9a779b18ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222447"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="e5a82-102">MultiplySI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e5a82-102">MultiplySI operation</span></span>

<span data-ttu-id="e5a82-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e5a82-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e5a82-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e5a82-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e5a82-105">Multiplicera signerat heltal `xs` med signerat heltal `ys` och lagra resultatet i `result` , vilket måste vara noll först.</span><span class="sxs-lookup"><span data-stu-id="e5a82-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e5a82-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e5a82-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="e5a82-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5a82-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e5a82-108">n-bitars multiplicand (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5a82-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="e5a82-109">gar: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5a82-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e5a82-110">n-bitars multiplikator (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5a82-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="e5a82-111">resultat: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5a82-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e5a82-112">2N-bitars resultat (SignedLittleEndian) måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="e5a82-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e5a82-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5a82-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

