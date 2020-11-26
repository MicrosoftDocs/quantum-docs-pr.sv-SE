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
# <a name="mcmtmask-user-defined-type"></a>MCMTMask-användardefinierad typ

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En typ som representerar en Toffoli-grind med flera mål.

Det första heltalet är en bitmask för kontroll linjer.  Bit index som anges motsvarar kontroll linje index.

Det andra heltalet är en bitmask för mål linjer.  Bit index som anges motsvarar mål linje index.

Bit indexen för båda heltalen måste vara åtskilda.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="controlmask--int"></a>ControlMask: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [int](xref:microsoft.quantum.lang-ref.int)

