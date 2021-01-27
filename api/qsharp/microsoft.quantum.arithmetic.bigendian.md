---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843382"
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