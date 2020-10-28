---
uid: Microsoft.Quantum.Core.Deprecated
title: Inaktuell användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727459"
---
# <a name="deprecated-user-defined-type"></a>Inaktuell användardefinierad typ

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paketfilerna [](https://nuget.org/packages/)


Compile-känt attribut som används för att markera en typ eller som kan anropas som föråldrad.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="newname--string"></a>Nyttnamn: [sträng](xref:microsoft.quantum.lang-ref.string)

Det fullständiga namnet på den typ eller det anrop som ska användas i stället.
Är inställt på den tomma strängen om en typ eller anropad har ersatts utan ersättning.