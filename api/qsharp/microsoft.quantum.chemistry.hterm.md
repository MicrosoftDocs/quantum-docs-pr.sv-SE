---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204138"
---
# <a name="hterm-user-defined-type"></a>HTerm-användardefinierad typ

Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formatet på data som skickas från C# till Q # för att representera en term i Hamiltonian.
Innebörden av de data som representeras bestäms av algoritmen som tar emot den.

```qsharp

newtype HTerm = (Int[], Double[]);
```

