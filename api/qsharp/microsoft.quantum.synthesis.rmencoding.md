---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: Funktionen RMEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202948"
---
# <a name="rmencoding-function"></a><span data-ttu-id="14fb3-102">Funktionen RMEncoding</span><span class="sxs-lookup"><span data-stu-id="14fb3-102">RMEncoding function</span></span>

<span data-ttu-id="14fb3-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="14fb3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="14fb3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14fb3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14fb3-105">{-1,1} kodning av ett booleskt sanningen-värde</span><span class="sxs-lookup"><span data-stu-id="14fb3-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="14fb3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="14fb3-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="14fb3-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="14fb3-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="14fb3-108">Booleskt värde</span><span class="sxs-lookup"><span data-stu-id="14fb3-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="14fb3-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="14fb3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="14fb3-110">1, om `b` är falskt, annars – 1</span><span class="sxs-lookup"><span data-stu-id="14fb3-110">1, if `b` is false, otherwise -1</span></span>