---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734075"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="df104-102">MCMTMask-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="df104-102">MCMTMask user defined type</span></span>

<span data-ttu-id="df104-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="df104-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="df104-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df104-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df104-105">En typ som representerar en Toffoli-grind med flera mål.</span><span class="sxs-lookup"><span data-stu-id="df104-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="df104-106">Det första heltalet är en bitmask för kontroll linjer.</span><span class="sxs-lookup"><span data-stu-id="df104-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="df104-107">Bit index som anges motsvarar kontroll linje index.</span><span class="sxs-lookup"><span data-stu-id="df104-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="df104-108">Det andra heltalet är en bitmask för mål linjer.</span><span class="sxs-lookup"><span data-stu-id="df104-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="df104-109">Bit index som anges motsvarar mål linje index.</span><span class="sxs-lookup"><span data-stu-id="df104-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="df104-110">Bit indexen för båda heltalen måste vara åtskilda.</span><span class="sxs-lookup"><span data-stu-id="df104-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="df104-111">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="df104-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="df104-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df104-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="df104-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df104-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

