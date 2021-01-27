---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Multiplicerai-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843032"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="f790f-102">Multiplicerai-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f790f-102">MultiplyI operation</span></span>

<span data-ttu-id="f790f-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f790f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f790f-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f790f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f790f-105">Multiplicera Heltal `xs` med heltal `ys` och lagra resultatet i `result` , som först måste vara noll.</span><span class="sxs-lookup"><span data-stu-id="f790f-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f790f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f790f-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f790f-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f790f-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f790f-108">$n $-bit multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f790f-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f790f-109">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f790f-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f790f-110">$n $-bit multiplikator (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f790f-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="f790f-111">resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f790f-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f790f-112">$2N $-bit result (LittleEndian) måste ha statusen $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="f790f-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f790f-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f790f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f790f-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f790f-114">Remarks</span></span>

<span data-ttu-id="f790f-115">Använder en vanlig Shift-och-Lägg-metod för att implementera multiplikationen.</span><span class="sxs-lookup"><span data-stu-id="f790f-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="f790f-116">Den kontrollerade versionen har förbättrats genom att du kopierade $x _i $ till en Ancilla-qubit som är villkorlig på kontrollen qubits och sedan styr additionen av Ancilla qubit.</span><span class="sxs-lookup"><span data-stu-id="f790f-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>