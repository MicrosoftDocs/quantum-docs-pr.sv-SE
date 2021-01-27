---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852814"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU-åtgärd

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementering av `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL




### <a name="selector--ts--unit--is-adj--ctl"></a>väljare: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL




### <a name="auxiliary--t"></a>hjälp: ' t




### <a name="system--s"></a>system: s





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="s"></a>Formulär

