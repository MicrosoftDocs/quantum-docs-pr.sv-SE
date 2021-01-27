---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: Funktionen JordanWignerGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: a75d46ef0b38fbcef99b7ab22454e1b5a9475b11
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837779"
---
# <a name="jordanwignergeneratorsystem-function"></a>Funktionen JordanWignerGeneratorSystem

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konverterar en Hamiltonian som beskrivs av `JWOptimizedHTerms` till en `GeneratorSystem` uttryckt i termer av den `GeneratorIndex` konvention som definierats i den här filen.

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Indata

### <a name="data--jwoptimizedhterms"></a>data: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

Beskrivning av Hamiltonian i `JWOptimizedHTerms` format.



## <a name="output--generatorsystem"></a>Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Representation av Hamiltonian som `GeneratorSystem` .