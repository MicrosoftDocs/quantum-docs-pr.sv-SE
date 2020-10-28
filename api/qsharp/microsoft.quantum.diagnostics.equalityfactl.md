---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: Funktionen EqualityFactL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727237"
---
# <a name="equalityfactl-function"></a>Funktionen EqualityFactL

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


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

