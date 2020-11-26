---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Funktionen QuantumROMQubitCount
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210411"
---
# <a name="quantumromqubitcount-function"></a>Funktionen QuantumROMQubitCount

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROMQubitCount är föråldrad. Använd <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> i stället.

Returnerar det totala antalet qubits som måste allokeras till den åtgärd som returnerades av `QuantumROM` .

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>Indata

### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mål felet $ \epsilon $.


### <a name="ncoeffs--int"></a>nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)

Antalet koefficienter som anges i `QuantumROM` .



## <a name="output--intintint"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))

## <a name="first-parameter"></a>Första parametern

En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.