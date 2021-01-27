---
uid: Microsoft.Quantum.Math.InverseModL
title: Funktionen InverseModL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851395"
---
# <a name="inversemodl-function"></a>Funktionen InverseModL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar $b $ så att $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Indata

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Talet inverteras


### <a name="modulus--bigint"></a>Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Den modul enligt vilken talen inverteras



## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Integer $b $ så att $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.