---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: Funktionen ContinuedFractionConvergentL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c10fcbbe63d3d4c7d6c56196768c1062be1ca350
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210938"
---
# <a name="continuedfractionconvergentl-function"></a>Funktionen ContinuedFractionConvergentL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Söker efter den fortsatta fraktions Convergent som ligger närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a>Indata

### <a name="fraction--bigfraction"></a>bråk: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)




### <a name="denominatorbound--bigint"></a>denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigfraction"></a>Utdata: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)

Fortsatt bråk som är närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`