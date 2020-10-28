---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Kvadratmetoden-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730459"
---
# <a name="squaresi-operation"></a><span data-ttu-id="62ee4-102">Kvadratmetoden-åtgärd</span><span class="sxs-lookup"><span data-stu-id="62ee4-102">SquareSI operation</span></span>

<span data-ttu-id="62ee4-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62ee4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62ee4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62ee4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62ee4-105">Fyrkantigt signerat heltal `xs` och lagra resultatet i `result` , vilket måste vara noll först.</span><span class="sxs-lookup"><span data-stu-id="62ee4-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="62ee4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="62ee4-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="62ee4-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62ee4-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="62ee4-108">n-bitars heltal till kvadrat (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62ee4-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="62ee4-109">resultat: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62ee4-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="62ee4-110">2N-bitars resultat (SignedLittleEndian) måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="62ee4-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62ee4-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62ee4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="62ee4-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="62ee4-112">Remarks</span></span>

<span data-ttu-id="62ee4-113">Implementeringen är beroende av IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="62ee4-113">The implementation relies on IntegerSquare.</span></span>