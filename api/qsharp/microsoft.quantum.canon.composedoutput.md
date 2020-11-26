---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Funktionen ComposedOutput
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207470"
---
# <a name="composedoutput-function"></a>Funktionen ComposedOutput

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar utdata från sammansättningen av `inner` och `outer` för en specifik indata.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Indata

### <a name="outer--u---v"></a>yttre: "U->" V




### <a name="inner--t---u"></a>inre: ' t-> ' U




### <a name="target--t"></a>mål: ' t





## <a name="output--v"></a>Utdata: ' V



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="u"></a>' U


### <a name="v"></a>' V

