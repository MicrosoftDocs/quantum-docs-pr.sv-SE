---
uid: Microsoft.Quantum.Intrinsic.Message
title: Meddelande funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849366"
---
# <a name="message-function"></a>Meddelande funktion

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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