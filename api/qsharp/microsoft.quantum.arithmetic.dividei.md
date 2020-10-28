---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Dela uppi-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731582"
---
# <a name="dividei-operation"></a><span data-ttu-id="86a28-102">Dela uppi-åtgärd</span><span class="sxs-lookup"><span data-stu-id="86a28-102">DivideI operation</span></span>

<span data-ttu-id="86a28-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="86a28-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="86a28-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86a28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86a28-105">Dividerar två Quantum-heltal.</span><span class="sxs-lookup"><span data-stu-id="86a28-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="86a28-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="86a28-106">Description</span></span>

<span data-ttu-id="86a28-107">`xs` kommer att hålla resten `xs - floor(xs/ys) * ys` och `result` hållas kvar `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="86a28-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="86a28-108">Indata</span><span class="sxs-lookup"><span data-stu-id="86a28-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="86a28-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86a28-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="86a28-110">$n $-bitars utdelning ersätts av resten.</span><span class="sxs-lookup"><span data-stu-id="86a28-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="86a28-111">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86a28-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="86a28-112">$n $-bit divisor</span><span class="sxs-lookup"><span data-stu-id="86a28-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="86a28-113">resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86a28-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="86a28-114">$n $-bit-resultatet måste vara i tillstånd $ \ket {0} $ initialt och kommer att ersättas av resultatet av heltals divisionen.</span><span class="sxs-lookup"><span data-stu-id="86a28-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86a28-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86a28-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="86a28-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="86a28-116">Remarks</span></span>

<span data-ttu-id="86a28-117">Använder en standard metod för att Shift-och-subtrahera för att implementera divisionen.</span><span class="sxs-lookup"><span data-stu-id="86a28-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="86a28-118">Den kontrollerade versionen är specialiserad så att subtraktionen inte kräver ytterligare kontroller.</span><span class="sxs-lookup"><span data-stu-id="86a28-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>