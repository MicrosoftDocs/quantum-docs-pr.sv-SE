---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Kvadratmetoden-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7fe4d27b974a06b019a2b15710fbc51b598027b4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221835"
---
# <a name="squaresi-operation"></a><span data-ttu-id="21462-102">Kvadratmetoden-åtgärd</span><span class="sxs-lookup"><span data-stu-id="21462-102">SquareSI operation</span></span>

<span data-ttu-id="21462-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="21462-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="21462-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="21462-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="21462-105">Fyrkantigt signerat heltal `xs` och lagra resultatet i `result` , vilket måste vara noll först.</span><span class="sxs-lookup"><span data-stu-id="21462-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="21462-106">Indata</span><span class="sxs-lookup"><span data-stu-id="21462-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="21462-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21462-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="21462-108">n-bitars heltal till kvadrat (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21462-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="21462-109">resultat: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21462-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="21462-110">2N-bitars resultat (SignedLittleEndian) måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="21462-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21462-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21462-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="21462-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="21462-112">Remarks</span></span>

<span data-ttu-id="21462-113">Implementeringen är beroende av IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="21462-113">The implementation relies on IntegerSquare.</span></span>