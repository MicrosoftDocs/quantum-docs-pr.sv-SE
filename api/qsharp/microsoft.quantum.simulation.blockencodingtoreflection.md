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
# <a name="blockencodingtoreflection-function"></a>Funktionen BlockEncodingToReflection

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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