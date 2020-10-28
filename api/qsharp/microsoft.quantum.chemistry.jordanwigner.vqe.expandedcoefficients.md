---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Funktionen ExpandedCoefficients
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727648"
---
# <a name="expandedcoefficients-function"></a>Funktionen ExpandedCoefficients

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paketfilerna [](https://nuget.org/packages/)


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