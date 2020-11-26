---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193632"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förbereder en qubit i blandat läge för maximally.

Den förbereder den aktuella qubit i läget $ \boldone/$2 genom att använda depolarisering Channel $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ WHERE $ \sigma \_ i $ är den $i $ th Pauli-operatorn och där $ \rho $ är en densitet som representerar ett blandat tillstånd.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En qubit vars tillstånd ska avsättas på det sätt som beskrivs ovan.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Det blandade State $ \boldone/$2 som beskriver resultatet av att tillämpa den här åtgärden på ett tillstånd beskriver implicit ett förväntat värde över slumpmässiga val som gjorts i den här åtgärden.
För alla enskilda program mappar den här åtgärden rent tillstånd till rent tillstånd, men den fungerar enligt beskrivningen i förväntan.
I synnerhet kan den här åtgärden användas i process-tomography för att mäta *icke-enhetens* komponenter i en kanal.