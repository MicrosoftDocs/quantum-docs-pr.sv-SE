---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827390"
---
# <a name="decodefromsteanecode-operation"></a>DecodeFromSteaneCode-åtgärd

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En inverterad kodnings åtgärd som mappar ett kodat Quantum-register till en kodad Quantum-register under ⟦ 7, 1, 3 ⟧ Steane Quantum Code.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Indata

### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

En matris med qubits som representerar det logiska tillstånd för kodade 5 qubit-kod.



## <a name="output--qubitqubit"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

En qubit-matris med längden 1 som representerar det avkodade läget i den första parametern, tillsammans med hjälp qubits i den andra parametern.

## <a name="remarks"></a>Kommentarer

Den valda avkodaren använder CSS-egenskapen för ⟦ 7, 1, 3 ⟧ Steane kod, dvs. den korrigerar X-fel och Z-fel separat. En egenskap i koden är att platsen för X, Z-korrigeringen som ska tillämpas är 3D-kodningen för X respektive Z-Syndrome när det betraktas som ett heltal.

## <a name="references"></a>Referenser

- D. Gottesman, "stabiliserings koder och Quantum Error Correction", Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)