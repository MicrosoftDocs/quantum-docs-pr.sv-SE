---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Kvadratiski-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846304"
---
# <a name="squarei-operation"></a><span data-ttu-id="d0880-102">Kvadratiski-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d0880-102">SquareI operation</span></span>

<span data-ttu-id="d0880-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d0880-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d0880-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d0880-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d0880-105">Beräknar kvadraten av heltalet `xs` i `result` , som måste vara noll först.</span><span class="sxs-lookup"><span data-stu-id="d0880-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d0880-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d0880-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d0880-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d0880-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d0880-108">$n $-bit Number till Square (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d0880-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="d0880-109">resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d0880-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d0880-110">$2N $-bit result (LittleEndian) måste ha statusen $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="d0880-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0880-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0880-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0880-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d0880-112">Remarks</span></span>

<span data-ttu-id="d0880-113">Använder en vanlig Shift-och-Lägg-metod för att beräkna fyr kanten.</span><span class="sxs-lookup"><span data-stu-id="d0880-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="d0880-114">Sparar $n-$1-qubits jämfört med den enkla lösningen som först kopierar x x innan en vanlig multiplikator appliceras och sedan ångrar kopierings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d0880-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>