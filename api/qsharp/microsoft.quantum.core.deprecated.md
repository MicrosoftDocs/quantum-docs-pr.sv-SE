---
uid: Microsoft.Quantum.Core.Deprecated
title: Inaktuell användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832090"
---
# <a name="deprecated-user-defined-type"></a>Inaktuell användardefinierad typ

Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Compile-känt attribut som används för att markera en typ eller som kan anropas som föråldrad.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="newname--string"></a>Nyttnamn: [sträng](xref:microsoft.quantum.lang-ref.string)

Det fullständiga namnet på den typ eller det anrop som ska användas i stället.
Är inställt på den tomma strängen om en typ eller anropad har ersatts utan ersättning.