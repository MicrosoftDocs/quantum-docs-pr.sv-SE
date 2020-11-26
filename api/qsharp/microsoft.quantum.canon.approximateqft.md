---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 97a410133e80cc5bffc810e9d6455baaee32364b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207708"
---
# <a name="approximateqft-operation"></a>ApproximateQFT-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använd den ungefärliga AQFT-transformeringen (Quantum Fourier Transform) till ett Quantum-register.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Ungefärlig parameter som avgör på vilken nivå de kontrollerade Z-rotationer som sker i QFT-kretsen rensas.

Den ungefärliga parametern a bestämmer rensnings nivån för Z-rotationer, d.v.s. en ∈ {0.. n} och alla Z-rotationer 2π/2 000 där k>a tas bort från QFT-kretsen. Det är känt att för k >= log ₂ (n) + log ₂ (1/ε) + 3 en kan vara kopplad | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Quantum-register för n-qubits som den ungefärliga Quantum Fourier-transformeringen tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

AQFT kräver Z-rotations grindar av formatet 2π/2 000 och Hadamard Gates.

Indata och utdata antas vara kodade i big endian encoding.

## <a name="references"></a>Referenser

- [*M. Roetteler, Th. Beth*, anv. algebra eng. Commune. Compute. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: Quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)