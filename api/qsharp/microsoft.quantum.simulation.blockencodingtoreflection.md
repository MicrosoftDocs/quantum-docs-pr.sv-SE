---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: Funktionen BlockEncodingToReflection
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847264"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="9c3c8-102">Funktionen BlockEncodingToReflection</span><span class="sxs-lookup"><span data-stu-id="9c3c8-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="9c3c8-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9c3c8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9c3c8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c3c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c3c8-105">Konverterar en `BlockEncoding` till motsvarande `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="9c3c8-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="9c3c8-106">Det innebär att med en `BlockEncoding` enhetlig $U $ som kodar en viss operatör $H $ of Interest, konverterar den till en `BlockEncodingReflection` $U $ som kodar samma Operator, men den uppfyller också $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="9c3c8-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="9c3c8-107">Detta ökar storleken på hjälp registren för $U $ med en qubit.</span><span class="sxs-lookup"><span data-stu-id="9c3c8-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="9c3c8-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9c3c8-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="9c3c8-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="9c3c8-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="9c3c8-110">En `BlockEncoding` enhetlig $U $ som ska konverteras till en reflektion.</span><span class="sxs-lookup"><span data-stu-id="9c3c8-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="9c3c8-111">Utdata: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="9c3c8-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="9c3c8-112">En enhetlig $U $ som agerar gemensamt på registren `a` och `s` att block-Encoder $H $ och uppfyller $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="9c3c8-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c3c8-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9c3c8-113">Remarks</span></span>

<span data-ttu-id="9c3c8-114">Detta ökar storleken på hjälp registren för $U $ med en qubit.</span><span class="sxs-lookup"><span data-stu-id="9c3c8-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="9c3c8-115">Referenser</span><span class="sxs-lookup"><span data-stu-id="9c3c8-115">References</span></span>

- <span data-ttu-id="9c3c8-116">Hamiltonian-simulering av Qubitization Guang lämnar demon Hao Low, Isak L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="9c3c8-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="9c3c8-117">Se även</span><span class="sxs-lookup"><span data-stu-id="9c3c8-117">See Also</span></span>

- [<span data-ttu-id="9c3c8-118">Microsoft. Quantum. simulering. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="9c3c8-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="9c3c8-119">Microsoft. Quantum. simulering. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="9c3c8-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)