---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727153"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode åtgärd

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paketfilerna [](https://nuget.org/packages/)


Syndrome mått och inversen av inbäddning.

$X $-och $Z $-stabilisatorer behandlas inte lika, vilket beror på det särskilda valet av kodnings kretsen.
Den här asymmetry leder till en annan Syndrome extraherings rutin.
En kan mäta Syndrome genom att mäta Pauli-operatorn för flera qubit direkt i kod staten, men för destillations ändamål returneras den logiska qubit till en enda qubit, i vilken Syndrome mätningar kan göras utan ytterligare ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Indata

### <a name="code--logicalregister"></a>kod: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Det logiska qubit och ett par med heltal för $X $-Syndrome och $Z $-syndrome.
De representerar index för koden qubit som en enskild $X $-eller $Z $-Error skulle ha orsakat den uppmätta syndrome.

## <a name="remarks"></a>Kommentarer

Observera att den här åtgärden inte har marker ATS som `internal` enhets test direkt beroende av den här åtgärden. Som en framtida förbättring bör enhets test omplaneras till enbart beroende på offentliga callables direkt.

> [!WARNING]
> Den här rutinen är anpassad till en viss kodnings krets för Steane 7 qubit-kod; om kodnings kretsen ändras kanske Syndrome-resultatet måste tolkas annorlunda.