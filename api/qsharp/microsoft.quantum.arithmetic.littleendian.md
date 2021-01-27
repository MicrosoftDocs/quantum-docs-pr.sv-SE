---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846571"
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