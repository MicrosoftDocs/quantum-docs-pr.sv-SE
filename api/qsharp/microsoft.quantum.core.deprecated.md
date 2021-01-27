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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="414d1-102">Inaktuell användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="414d1-102">Deprecated user defined type</span></span>

<span data-ttu-id="414d1-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="414d1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="414d1-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="414d1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="414d1-105">Compile-känt attribut som används för att markera en typ eller som kan anropas som föråldrad.</span><span class="sxs-lookup"><span data-stu-id="414d1-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="414d1-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="414d1-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="414d1-107">Nyttnamn: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="414d1-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="414d1-108">Det fullständiga namnet på den typ eller det anrop som ska användas i stället.</span><span class="sxs-lookup"><span data-stu-id="414d1-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="414d1-109">Är inställt på den tomma strängen om en typ eller anropad har ersatts utan ersättning.</span><span class="sxs-lookup"><span data-stu-id="414d1-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>