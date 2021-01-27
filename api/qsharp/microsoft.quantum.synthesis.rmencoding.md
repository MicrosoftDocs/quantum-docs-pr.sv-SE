---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: Funktionen RMEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855329"
---
# <a name="rmencoding-function"></a><span data-ttu-id="fb8a5-102">Funktionen RMEncoding</span><span class="sxs-lookup"><span data-stu-id="fb8a5-102">RMEncoding function</span></span>

<span data-ttu-id="fb8a5-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="fb8a5-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="fb8a5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb8a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb8a5-105">{-1,1} kodning av ett booleskt sanningen-värde</span><span class="sxs-lookup"><span data-stu-id="fb8a5-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="fb8a5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fb8a5-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="fb8a5-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fb8a5-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fb8a5-108">Booleskt värde</span><span class="sxs-lookup"><span data-stu-id="fb8a5-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="fb8a5-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb8a5-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb8a5-110">1, om `b` är falskt, annars – 1</span><span class="sxs-lookup"><span data-stu-id="fb8a5-110">1, if `b` is false, otherwise -1</span></span>