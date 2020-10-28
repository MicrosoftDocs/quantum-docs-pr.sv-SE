---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731526"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="944a8-102">GreaterThan-åtgärd</span><span class="sxs-lookup"><span data-stu-id="944a8-102">GreaterThan operation</span></span>

<span data-ttu-id="944a8-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="944a8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="944a8-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="944a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="944a8-105">Använder en större än-jämförelse mellan två heltal som är kodade i qubit-register, och vänder en mål-qubit baserat på resultatet av jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="944a8-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="944a8-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="944a8-106">Description</span></span>

<span data-ttu-id="944a8-107">Utför en strikt större än jämförelse av två heltal $x $ och $y $, kodade i qubit registrerar XS och gar.</span><span class="sxs-lookup"><span data-stu-id="944a8-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="944a8-108">Om $x > y $, kommer resultatet qubit att vändas, annars kommer resultatet qubit att behålla sitt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="944a8-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="944a8-109">Indata</span><span class="sxs-lookup"><span data-stu-id="944a8-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="944a8-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="944a8-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="944a8-111">LittleEndian qubit register encoding First Integer $x $.</span><span class="sxs-lookup"><span data-stu-id="944a8-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="944a8-112">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="944a8-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="944a8-113">LittleEndian qubit register encoding det andra heltalet $y $.</span><span class="sxs-lookup"><span data-stu-id="944a8-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="944a8-114">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="944a8-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="944a8-115">En enda qubit som kommer att vändas om $x > y $.</span><span class="sxs-lookup"><span data-stu-id="944a8-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="944a8-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="944a8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="944a8-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="944a8-117">Remarks</span></span>

<span data-ttu-id="944a8-118">Använder det stick som $x-y = (x ' + y) ' $, där ' anger ett komplement.</span><span class="sxs-lookup"><span data-stu-id="944a8-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="944a8-119">Referenser</span><span class="sxs-lookup"><span data-stu-id="944a8-119">References</span></span>

- <span data-ttu-id="944a8-120">Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum krusning-Drive-extra kretsen", 2004.</span><span class="sxs-lookup"><span data-stu-id="944a8-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="944a8-121">Thomas Haener, Martin Roetteler, krysta M. Svore: "factoring med 2n + 2 qubits med Toffoli-baserad modulär multiplikation", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="944a8-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>