---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Funktionen FiveQubitCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200891"
---
# <a name="fivequbitcode-function"></a>Funktionen FiveQubitCode

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar ett QECC-värde som representerar ⟦ 5, 1, 3 ⟧ kod kodare och avkodare med Syndrome på plats.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Utdata: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Returnerar en implementering av en Quantum-fel korrigerings kod genom att ange en `QECC` typ.

## <a name="remarks"></a>Kommentarer

Den här koden hittades oberoende av följande två dokument:

- C. &. Bennett, D. DiVincenzo, J. A. Smolin och W. K. Wootters, "blandat läge entanglement och Quantum Error Correction", inventering. Rev. A, 54 (1996) s. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 och
- R. Laflamme, C. Miquel, J. P. Paz och W. H. Zurek, "fel korrigerings kod för perfekt Quantum", "inventering. Rev. lett. 77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019