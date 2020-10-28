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
# <a name="message-function"></a>Meddelande funktion

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paketfilerna [](https://nuget.org/packages/)


Loggar ett meddelande.

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>Indata

### <a name="msg--string"></a>Msg: [sträng](xref:microsoft.quantum.lang-ref.string)

Meddelandet som ska rapporteras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Det speciella beteendet för den här funktionen är Simulator-beroende, men i de flesta fall kommer det angivna meddelandet att skrivas till-konsolen.