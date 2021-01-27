---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842979"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Visar ett Quantum-register om ett angivet klassiskt heltal.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Med ett Quantum-register inlednings vis i status $ \ sum_i \ alpha_i \ket{i} $, där varje $ \ket{i} $ är ett bas tillstånd som representerar ett heltal $i $, visar status för registret om grund tillstånd för ett angivet heltal $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Indata

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Det klassiska heltalet som indexerar det grundläggande tillstånd som ska reflekteras.


### <a name="reg--littleendian"></a>REG: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den här åtgärden implementeras på plats utan explicit allokering av ytterligare hjälp-qubits.