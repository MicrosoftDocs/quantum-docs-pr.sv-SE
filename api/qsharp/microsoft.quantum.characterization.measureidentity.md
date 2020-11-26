---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216123"
---
# <a name="measureidentity-operation"></a>MeasureIdentity-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mäter identitets operatören på ett register över qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Indata

### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registret som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatvärdet `Zero` .

## <a name="remarks"></a>Kommentarer

Eftersom $ \boldone $ endast har eigenvalue $1 $, och inte har ett negativt eigenvalue, returnerar den här åtgärden alltid `Zero` , som motsvarar eigenvalue $ + 1 = (-1) ^ 0 $, och orsakar ingen komprimering av status för `register` .

Den här åtgärden är inte användbar, men är användbar i samband med process-Tomography, eftersom den ger information om spårning av väntande processer i en Quantum-process.
I synnerhet bör en mål dator med förlust mått ersätta den här åtgärden med en faktisk mätning på $ \boldone $.