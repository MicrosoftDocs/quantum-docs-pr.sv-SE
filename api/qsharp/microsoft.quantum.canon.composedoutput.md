---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Funktionen ComposedOutput
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840893"
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

