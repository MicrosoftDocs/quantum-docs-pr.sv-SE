---
uid: Microsoft.Quantum.Intrinsic.Message
title: Meddelande funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199020"
---
# <a name="message-function"></a><span data-ttu-id="da677-102">Meddelande funktion</span><span class="sxs-lookup"><span data-stu-id="da677-102">Message function</span></span>

<span data-ttu-id="da677-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="da677-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="da677-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="da677-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="da677-105">Loggar ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="da677-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="da677-106">Indata</span><span class="sxs-lookup"><span data-stu-id="da677-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="da677-107">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="da677-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="da677-108">Meddelandet som ska rapporteras.</span><span class="sxs-lookup"><span data-stu-id="da677-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da677-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da677-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da677-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="da677-110">Remarks</span></span>

<span data-ttu-id="da677-111">Det speciella beteendet för den här funktionen är Simulator-beroende, men i de flesta fall kommer det angivna meddelandet att skrivas till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="da677-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>