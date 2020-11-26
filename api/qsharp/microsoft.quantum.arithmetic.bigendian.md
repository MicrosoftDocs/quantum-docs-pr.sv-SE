---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223671"
---
# <a name="bigendian-user-defined-type"></a>BigEndian-användardefinierad typ

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Registrera att koda ett osignerat heltal i big-endian-ordning. Qubit med index `0` kodar den högsta biten av ett osignerat heltal.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Kommentarer

Vi förkortar `BigEndian` som `BE` i dokumentationen.