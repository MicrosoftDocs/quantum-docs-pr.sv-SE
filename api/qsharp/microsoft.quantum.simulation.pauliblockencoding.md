---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Funktionen PauliBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730915"
---
# <a name="pauliblockencoding-function"></a>Funktionen PauliBlockEncoding

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Skapar en typ av block kodning för en Hamiltonian.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ beskrivs av en summa av Pauli-termer $P _j $, var och en med verklig koefficient $ \ alpha_j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Indata

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

En `GeneratorSystem` som beskriver $H $ som en summa av Pauli villkor



## <a name="output--doubleblockencodingreflection"></a>Utdata: ([dubbel](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Första parametern

En-norm för koefficienter $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Andra parameter

En `BlockEncodingReflection` enhetlig $U $ Hamiltonian $H $. Eftersom den här lösningen uppfyller $U ^ 2 = I $, är det också en reflektion.

## <a name="remarks"></a>Kommentarer

Detta erhålls genom att förbereda och stoppa statusen $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, och skapa en multiplicering-kontrollerad <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> och <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .