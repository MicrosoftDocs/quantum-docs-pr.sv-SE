---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Funktionen ExpandedCoefficients
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835624"
---
# <a name="expandedcoefficients-function"></a>Funktionen ExpandedCoefficients

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Utökar komprimerings representationen av Jordan-Wigner-koefficienter för att kunna hämta en en-till-en-mappning mellan dessa och Pauli villkor.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Indata

### <a name="coeff--double"></a>coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]

En matris med koefficienter som läses från Jordan-Wigner Hamiltonian data struktur.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner termns typ.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]

Expanderade matriser med koefficienter, en per Pauli-period.