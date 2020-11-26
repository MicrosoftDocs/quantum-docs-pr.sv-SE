---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222787"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian-användardefinierad typ

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Registrera att koda ett osignerat heltal i litet endian-ordning. Qubit med index `0` kodar den lägsta biten i ett osignerat heltal.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Kommentarer

Vi förkortar `LittleEndian` som `LE` i dokumentationen.