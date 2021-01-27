---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: Funktionen EqualityFactL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829148"
---
# <a name="equalityfactl-function"></a>Funktionen EqualityFactL

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förutsätter att en klassisk BigInt-variabel har det förväntade värdet.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Indata

### <a name="actual--bigint"></a>faktiskt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det tal som ska kontrol leras.


### <a name="expected--bigint"></a>förväntat: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det förväntade värdet.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Fel meddelande strängen som ska användas när kontrollen utlöses.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

