---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: Funktionen ComposedOutput
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728836"
---
# <a name="composedoutput-function"></a>Funktionen ComposedOutput

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


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

