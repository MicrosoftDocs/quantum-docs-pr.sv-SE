---
uid: Microsoft.Quantum.Synthesis.Extended
title: Utökad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855479"
---
# <a name="extended-function"></a>Utökad funktion

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utökar ett spektrum med inverterade koefficienter

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Indata

### <a name="spectrum--int"></a>spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]

Spectral-koefficienter



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

Koefficienter följt av inverterad kopia

## <a name="example"></a>Exempel

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```