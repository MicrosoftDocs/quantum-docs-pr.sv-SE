---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851812"
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