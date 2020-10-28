---
uid: Microsoft.Quantum.Intrinsic.Message
title: Meddelande funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726667"
---
# <a name="message-function"></a><span data-ttu-id="3c7cc-102">Meddelande funktion</span><span class="sxs-lookup"><span data-stu-id="3c7cc-102">Message function</span></span>

<span data-ttu-id="3c7cc-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3c7cc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3c7cc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c7cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c7cc-105">Loggar ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="3c7cc-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3c7cc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3c7cc-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="3c7cc-107">Msg: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3c7cc-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3c7cc-108">Meddelandet som ska rapporteras.</span><span class="sxs-lookup"><span data-stu-id="3c7cc-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c7cc-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c7cc-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c7cc-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3c7cc-110">Remarks</span></span>

<span data-ttu-id="3c7cc-111">Det speciella beteendet för den här funktionen är Simulator-beroende, men i de flesta fall kommer det angivna meddelandet att skrivas till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="3c7cc-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>