---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: Funktionen BlockEncodingToReflection
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732115"
---
# <a name="blockencodingtoreflection-function"></a>Funktionen BlockEncodingToReflection

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Konverterar en `BlockEncoding` till motsvarande `BLockEncodingReflection` .

Det innebär att med en `BlockEncoding` enhetlig $U $ som kodar en viss operatör $H $ of Interest, konverterar den till en `BlockEncodingReflection` $U $ som kodar samma Operator, men den uppfyller också $U ^ \Dagger = U $.
Detta ökar storleken på hjälp registren för $U $ med en qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Indata

### <a name="blockencoding--blockencoding"></a>blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

En `BlockEncoding` enhetlig $U $ som ska konverteras till en reflektion.



## <a name="output--blockencodingreflection"></a>Utdata: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

En enhetlig $U $ som agerar gemensamt på registren `a` och `s` att block-Encoder $H $ och uppfyller $U ^ \Dagger = U $.

## <a name="remarks"></a>Kommentarer

Detta ökar storleken på hjälp registren för $U $ med en qubit.

## <a name="references"></a>Referenser

- Hamiltonian-simulering av Qubitization Guang lämnar demon Hao Low, Isak L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulering. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)