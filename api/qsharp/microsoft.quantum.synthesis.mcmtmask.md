---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203032"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="d12af-102">MCMTMask-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d12af-102">MCMTMask user defined type</span></span>

<span data-ttu-id="d12af-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d12af-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d12af-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d12af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d12af-105">En typ som representerar en Toffoli-grind med flera mål.</span><span class="sxs-lookup"><span data-stu-id="d12af-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="d12af-106">Det första heltalet är en bitmask för kontroll linjer.</span><span class="sxs-lookup"><span data-stu-id="d12af-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="d12af-107">Bit index som anges motsvarar kontroll linje index.</span><span class="sxs-lookup"><span data-stu-id="d12af-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="d12af-108">Det andra heltalet är en bitmask för mål linjer.</span><span class="sxs-lookup"><span data-stu-id="d12af-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="d12af-109">Bit index som anges motsvarar mål linje index.</span><span class="sxs-lookup"><span data-stu-id="d12af-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="d12af-110">Bit indexen för båda heltalen måste vara åtskilda.</span><span class="sxs-lookup"><span data-stu-id="d12af-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="d12af-111">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="d12af-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="d12af-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d12af-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="d12af-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d12af-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

