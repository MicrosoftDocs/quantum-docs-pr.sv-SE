---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Kvadratiski-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221869"
---
# <a name="squarei-operation"></a><span data-ttu-id="3f5d2-102">Kvadratiski-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3f5d2-102">SquareI operation</span></span>

<span data-ttu-id="3f5d2-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3f5d2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3f5d2-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3f5d2-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3f5d2-105">Beräknar kvadraten av heltalet `xs` i `result` , som måste vara noll först.</span><span class="sxs-lookup"><span data-stu-id="3f5d2-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3f5d2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3f5d2-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="3f5d2-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f5d2-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f5d2-108">$n $-bit Number till Square (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f5d2-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="3f5d2-109">resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f5d2-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f5d2-110">$2N $-bit result (LittleEndian) måste ha statusen $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="3f5d2-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f5d2-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f5d2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3f5d2-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3f5d2-112">Remarks</span></span>

<span data-ttu-id="3f5d2-113">Använder en vanlig Shift-och-Lägg-metod för att beräkna fyr kanten.</span><span class="sxs-lookup"><span data-stu-id="3f5d2-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="3f5d2-114">Sparar $n-$1-qubits jämfört med den enkla lösningen som först kopierar x x innan en vanlig multiplikator appliceras och sedan ångrar kopierings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="3f5d2-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>