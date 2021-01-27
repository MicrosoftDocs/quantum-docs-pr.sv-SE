---
uid: Microsoft.Quantum.Bitwise.Xor
title: Funktionen XOR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842084"
---
# <a name="xor-function"></a><span data-ttu-id="f9cde-102">Funktionen XOR</span><span class="sxs-lookup"><span data-stu-id="f9cde-102">Xor function</span></span>

<span data-ttu-id="f9cde-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f9cde-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f9cde-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f9cde-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f9cde-105">Returnerar den bitvisa uteslutande eller (XOR) av två heltal.</span><span class="sxs-lookup"><span data-stu-id="f9cde-105">Returns the bitwise exclusive-OR (XOR) of two integers.</span></span>
<span data-ttu-id="f9cde-106">Detta utför samma beräkning som den inbyggda `^^^` operatorn.</span><span class="sxs-lookup"><span data-stu-id="f9cde-106">This performs the same computation as the built-in `^^^` operator.</span></span>

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f9cde-107">Indata</span><span class="sxs-lookup"><span data-stu-id="f9cde-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f9cde-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9cde-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="f9cde-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9cde-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="f9cde-110">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9cde-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="f9cde-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="f9cde-111">Example</span></span>

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a><span data-ttu-id="f9cde-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f9cde-112">Remarks</span></span>

<span data-ttu-id="f9cde-113">Mer information finns i [C# ^-operatorn](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) .</span><span class="sxs-lookup"><span data-stu-id="f9cde-113">See the [C# ^ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) for more details.</span></span>