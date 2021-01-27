---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: Funktionen HTermsToGenSys
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851768"
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