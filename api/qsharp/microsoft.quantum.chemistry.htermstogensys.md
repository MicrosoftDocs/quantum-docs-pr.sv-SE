---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: Funktionen HTermsToGenSys
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204121"
---
# <a name="htermstogensys-function"></a>Funktionen HTermsToGenSys

Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konverterar ett Hamiltonian i `HTerm[]` data format till en GeneratorSystem.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Indata

### <a name="data--hterm"></a>data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Indata i `HTerm[]` format.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)[]

Ytterligare information har lagts till i GeneratorIndex.



## <a name="output--generatorsystem"></a>Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

En GeneratorSystem som representerar en Hamiltonian som representeras av indata `data` .