---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Funktionen QuantumWalkByQubitization
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734118"
---
# <a name="quantumwalkbyqubitization-function"></a>Funktionen QuantumWalkByQubitization

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Konverterar en block kodnings reflektion till en Quantum-LED.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Beskrivning

Utifrån en `BlockEncodingReflection` person som representeras av en enhetlig $U $ som kodar en viss operatör $H $ of Interest, konverterar den till en Quantum-sats $W $ som innehåller spektrumet $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Indata

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

En `BlockEncodingReflection` enhetlig $U $ som ska konverteras till en Quantum-LED.



## <a name="output--qubitqubit--unit-adj--ctl"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En Quantum-$W $ som agerar gemensamt på registren `a` och `s` som blockerar-kodar $H $ och innehåller spektrumet $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Referenser

- Hamiltonian-simulering av Qubitization Guang lämnar demon Hao Low, Isak L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulering. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)