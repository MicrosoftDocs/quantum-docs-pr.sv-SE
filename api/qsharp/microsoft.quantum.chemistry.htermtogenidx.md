---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: Funktionen HTermToGenIdx
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216038"
---
# <a name="htermtogenidx-function"></a>Funktionen HTermToGenIdx

Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konverterar en Hamiltonian-term i `HTerm` data format till en GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Indata

### <a name="term--hterm"></a>term: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Indata i `HTerm` format.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)[]

Ytterligare information har lagts till i GeneratorIndex.



## <a name="output--generatorindex"></a>Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

En GeneratorIndex representerar en Hamiltonian-term som representeras av `term` , tillsammans med ytterligare information som lagts till av `termType` .