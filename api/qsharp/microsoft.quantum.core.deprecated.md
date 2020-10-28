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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="82f22-102">Inaktuell användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="82f22-102">Deprecated user defined type</span></span>

<span data-ttu-id="82f22-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="82f22-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="82f22-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82f22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82f22-105">Compile-känt attribut som används för att markera en typ eller som kan anropas som föråldrad.</span><span class="sxs-lookup"><span data-stu-id="82f22-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="82f22-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="82f22-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="82f22-107">Nyttnamn: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="82f22-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="82f22-108">Det fullständiga namnet på den typ eller det anrop som ska användas i stället.</span><span class="sxs-lookup"><span data-stu-id="82f22-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="82f22-109">Är inställt på den tomma strängen om en typ eller anropad har ersatts utan ersättning.</span><span class="sxs-lookup"><span data-stu-id="82f22-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>