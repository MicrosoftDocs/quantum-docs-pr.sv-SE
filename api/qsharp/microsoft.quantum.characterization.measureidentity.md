---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728185"
---
# <a name="measureidentity-operation"></a>MeasureIdentity-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paketfilerna [](https://nuget.org/packages/)


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