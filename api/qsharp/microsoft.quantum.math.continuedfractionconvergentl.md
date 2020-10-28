---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: Funktionen ContinuedFractionConvergentL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733118"
---
# <a name="continuedfractionconvergentl-function"></a>Funktionen ContinuedFractionConvergentL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Söker efter den fortsatta fraktions Convergent som ligger närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a>Indata

### <a name="fraction--bigfraction"></a>bråk: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)




### <a name="denominatorbound--bigint"></a>denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigfraction"></a>Utdata: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)

Fortsatt bråk som är närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`