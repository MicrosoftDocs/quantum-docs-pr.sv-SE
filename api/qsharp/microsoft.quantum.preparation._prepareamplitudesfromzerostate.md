---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: _PrepareAmplitudesFromZeroState åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 94563632d514f66608b14c264a73bdfcc6f50982
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854449"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a>_PrepareAmplitudesFromZeroState åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med tanke på en uppsättning koefficienter och ett litet endian-kodat Quantum-register för unentangled qubits, som alla är i läget noll, förbereder ett tillstånd i detta register som beskrivs av de angivna koefficienterna. Använder delläges emulering om det stöds av målet.

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Indata

### <a name="coefficients--complexpolar"></a>koefficienter: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

