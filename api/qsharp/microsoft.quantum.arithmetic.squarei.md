---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Kvadratiski-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730462"
---
# <a name="squarei-operation"></a><span data-ttu-id="5c80c-102">Kvadratiski-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5c80c-102">SquareI operation</span></span>

<span data-ttu-id="5c80c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5c80c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5c80c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c80c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c80c-105">Beräknar kvadraten av heltalet `xs` i `result` , som måste vara noll först.</span><span class="sxs-lookup"><span data-stu-id="5c80c-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="5c80c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5c80c-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="5c80c-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5c80c-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5c80c-108">$n $-bit Number till Square (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5c80c-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="5c80c-109">resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5c80c-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5c80c-110">$2N $-bit result (LittleEndian) måste ha statusen $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="5c80c-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c80c-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c80c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5c80c-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5c80c-112">Remarks</span></span>

<span data-ttu-id="5c80c-113">Använder en vanlig Shift-och-Lägg-metod för att beräkna fyr kanten.</span><span class="sxs-lookup"><span data-stu-id="5c80c-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="5c80c-114">Sparar $n-$1-qubits jämfört med den enkla lösningen som först kopierar x x innan en vanlig multiplikator appliceras och sedan ångrar kopierings åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5c80c-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>