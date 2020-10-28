---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728143"
---
# <a name="hterm-user-defined-type"></a>HTerm-användardefinierad typ

Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)

Paketfilerna [](https://nuget.org/packages/)


Formatet på data som skickas från C# till Q # för att representera en term i Hamiltonian.
Innebörden av de data som representeras bestäms av algoritmen som tar emot den.

```qsharp

newtype HTerm = (Int[], Double[]);
```

