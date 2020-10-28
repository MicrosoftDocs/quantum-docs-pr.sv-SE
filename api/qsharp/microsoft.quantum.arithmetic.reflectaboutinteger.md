---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730579"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paketfilerna [](https://nuget.org/packages/)


Visar ett Quantum-register om ett angivet klassiskt heltal.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Beskrivning

Med ett Quantum-register inlednings vis i status $ \ sum_i \ alpha_i \ket{i} $, där varje $ \ket{i} $ är ett bas tillstånd som representerar ett heltal $i $, visar status för registret om grund tillstånd för ett angivet heltal $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Indata

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Det klassiska heltalet som indexerar det grundläggande tillstånd som ska reflekteras.


### <a name="reg--littleendian"></a>REG: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den här åtgärden implementeras på plats utan explicit allokering av ytterligare hjälp-qubits.